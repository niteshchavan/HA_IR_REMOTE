# Home Assistant IR Remote Control
Control Home assistant lights with any IR remote 

# Source

https://developers.home-assistant.io/docs/api/rest/


# Edit Home assistant configuration.yaml and add api:
nano .homeassistant/configuration.yaml
```
api:
```
save and close.

All API calls have to be accompanied by the header Authorization: Bearer ABCDEFGH, where ABCDEFGH is replaced by your token. You can obtain a token ("Long-Lived Access Token") by logging into the frontend using a web browser, and going to your profile http://IP_ADDRESS:8123/profile.

# Test your api access
```
curl -X POST -H "Authorization: Bearer ABCDEFGH" \
  -H "Content-Type: application/json" \
  -d '{"entity_id": "switch.christmas_lights"}' \
  http://localhost:8123/api/services/switch/toggle
```

# Install and setup IR reciver using below source
https://github.com/niteshchavan/IR-Controller

#After installing copy key.conf in
```
/etc/triggerhappy/triggers.d/key.conf
```

# Restart triggerhappy daemon
```
systemctl daemon-reload && systemctl restart triggerhappy.service
```
