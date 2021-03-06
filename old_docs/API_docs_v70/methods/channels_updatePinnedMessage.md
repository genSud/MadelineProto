---
title: channels.updatePinnedMessage
description: channels.updatePinnedMessage parameters, return type and example
---
## Method: channels.updatePinnedMessage  
[Back to methods index](index.md)


### Parameters:

| Name     |    Type       | Required |
|----------|---------------|----------|
|silent|[Bool](../types/Bool.md) | Optional|
|channel|[InputChannel](../types/InputChannel.md) | Optional|
|id|[int](../types/int.md) | Yes|


### Return type: [Updates](../types/Updates.md)

### Can bots use this method: **YES**


### Errors this method can return:

| Error    | Description   |
|----------|---------------|
|CHANNEL_INVALID|The provided channel is invalid|
|CHAT_ADMIN_REQUIRED|You must be an admin in this chat to do this|
|CHAT_ID_INVALID|The provided chat id is invalid|
|CHAT_NOT_MODIFIED|The pinned message wasn't modified|


### Example:


```
$MadelineProto = new \danog\MadelineProto\API();
$MadelineProto->session = 'mySession.madeline';
if (isset($token)) { // Login as a bot
    $MadelineProto->bot_login($token);
}
if (isset($number)) { // Login as a user
    $MadelineProto->phone_login($number);
    $code = readline('Enter the code you received: '); // Or do this in two separate steps in an HTTP API
    $MadelineProto->complete_phone_login($code);
}

$Updates = $MadelineProto->channels->updatePinnedMessage(['silent' => Bool, 'channel' => InputChannel, 'id' => int, ]);
```

Or, if you're using the [PWRTelegram HTTP API](https://pwrtelegram.xyz):

### As a bot:

POST/GET to `https://api.pwrtelegram.xyz/botTOKEN/madeline`

Parameters:

* method - channels.updatePinnedMessage
* params - `{"silent": Bool, "channel": InputChannel, "id": int, }`



### As a user:

POST/GET to `https://api.pwrtelegram.xyz/userTOKEN/channels.updatePinnedMessage`

Parameters:

silent - Json encoded Bool

channel - Json encoded InputChannel

id - Json encoded int




Or, if you're into Lua:

```
Updates = channels.updatePinnedMessage({silent=Bool, channel=InputChannel, id=int, })
```

