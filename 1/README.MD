### Preparation
* Create aliases: k, kex, kc, kr, kn
<details>
  <summary>Spoiler warning</summary>
  
  Spoiler text. Note that it's important to have a space after the summary tag. You should be able to write any markdown you want inside the `<details>` tag... just make sure you close `<details>` afterward.
  
  ```javascript
  console.log("I'm a code block!");
  ```
  
</details>
### Namespace
* Create namespace `scenario1`. All following objects are created inside this namespace
### Deployment
* Create deployment named `nginx` with image `nginx:1.16` with 2 replicas with attached service on port `80`
* Get service IP address
* Run busybox container and bash into it. Curl the service IP address. Note the output.
### ConfigMap
* Create ConfigMap `index` from file `index.html`
* Create ConfigMap `env-vars` from file `config.env`
* Create ConfigMap `env-title` with variable `title` equal to `CKAD is easy`
* Change deployment and mount `index` to `/usr/share/nginx/html` path
* Add environment variables from `env-vars`
* Add environment variable `title` from `env-title` as `TITLE` environment variable
* Add command that runs `echo "$HELLO. $TITLE. $BYE. " > /usr/share/nginx/html/hello.html; nginx -v >> /usr/share/nginx/html/hello.html`
* Bash into busybox container and curl service again. You should get different output. Add `/hello.html` to the url, you should see the generated text.
