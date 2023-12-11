# Socket.io v2 Client Engine for Artillery v2.0

This socket.io artillery engine uses version 2 of the socket.io client, to be used with running load tests against version 2 socket.io servers.

Add the engine to your project:

```sh
npm install artillery-engine-socketio-v2@https://github.com/bioneos/artillery-engine-socketio-v2 --save
```

In test `.yml` file specify `socketio-v2` as an engine to be used in the test:

```yaml
config:
  engines:
    socketio-v2: {}
```

and then in each scenario specify it as the engine:

```yaml
scenarios:
  - name: Socket.io test
    engine: socketio-v2
    flow:
      # send chatroom message
      - emit:
          channel: "send-message"
          data:
            chatroomId: 102
            text_content: "Test message from vuser: {{ $uuid }}"
```
