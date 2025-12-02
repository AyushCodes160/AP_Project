payload:
{
  roomId: string,
  user: { id, name }
}
ack:
{
  success: true,
  users: [...]
}

### leave_room
payload:
{
  roomId: string,
  userId: string
}
ack:
{
  success: true
}

### code_update
payload:
{
  roomId: string,
  userId: string,
  delta: {...},
  fullText?: string,
  timestamp: number
}
ack:
{
  receivedAt: string
}

### run_code
payload:
{
  roomId: string,
  userId: string,
  language: string,
  code: string
}
ack:
{
  jobId: string
}
result_event:
{
  jobId: string,
  stdout: string,
  stderr: string,
  exitCode: number,
  duration: number
}

### presence_update
payload:
{
  roomId: string,
  userId: string,
  status: 'idle' | 'active'
}
ack:
{
  success: true
}

RULE: If you modify a socket event or payload field, update this file and request review from Person A + Person C.
