# helm-dependencies-demo

```
helm install demo .
```

Interesting files:
- [Chart.yaml](Chart.yaml) defines the alias `server` for the subchart `http-server`
- [values.yaml](values.yaml) uses templates in `server.htmlFolder` value. The templates here are in the scope of the subchart!
- [templates/_helpers.tpl](templates/_helpers.tpl) defines the named template `http-client.server_url`
- [templates/deployment.yaml](templates/deployment.yaml) uses the named template `http-client.server_url`
- [charts/http-server/templates/configmap.yaml](charts/http-server/templates/configmap.yaml) uses the `tpl` function to evaluate the templates in the `htmlFolder` values
