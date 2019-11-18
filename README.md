# vue-status-page

🎯Simple light vue project that checkup services by pinging them  ([Demo page](http://vue-status-page.bioudi-dev.com)).

---

## Project setup

```
npm install
```

## Configuration

You can add your services in this file named [config.js](https://github.com/bioudi/vue-status-page/blob/master/config.js).


for every service you have three parameter to indicate:

- endpoint: endpoint to test (required).
- isWebsite: if it's a website or not (required).
- port: port to test (optional).

```
{
    "retryInterval": "30", // in seconds
    "services": {
        "Personal website": {
            "endpoint": "https://aminebioudi.com",
            "isWebsite": true,
            "port": 443
        },
        "Google": {
            "endpoint": "https://google.com",
            "isWebsite": true
        },
        "RandomApi": {
            "endpoint": "https://od-api-demo.oxforddictionaries.com/api/v1/filters",
            "isWebsite": false
        }
    },
    "jiraCloud": {
        "enabled": false
    }
}
```

### Compiles and hot-reloads for development

```
npm run serve
```

### Compiles and minifies for production

```
npm run build
```

### Lints and fixes files

```
npm run lint
```

### Customize configuration

See [Configuration Reference](https://cli.vuejs.org/config/).
