
## Status: Experimental

This is currently an **experimental** module. Future maintenance is not guaranteed. Register your interest by starring this project on GitHub.

During experimentation, this module can be installed using:
```shell
npm install --save https://github.com/zebulonj/fetch-plus/archive/next.tar.gz
```

## Usage

This module conforms to, and is a superset of, the API documented at:
https://github.github.io/fetch/.

## Sugar

### Access to the XHR Object

This module adds direct access to the XMLHttpRequest object, for use cases not supported by the `fetch` specification (for example, progress tracking).

```
fetch( '/', {
  method: 'POST',
  xhr: xhr => {
    xhr.addEventListener( 'progress', event => {
      if ( event.lengthComputable ) {
        const percentComplete = event.loaded / event.total;
      } else {
        // Unable to compute progress information since the total size is unknown.
      }
    });
  },
  body: data
}).then( ... );
```

[fetch specification]: https://fetch.spec.whatwg.org
[cors]: https://developer.mozilla.org/en-US/docs/Web/HTTP/Access_control_CORS
  "Cross-origin resource sharing"
[csrf]: https://www.owasp.org/index.php/Cross-Site_Request_Forgery_(CSRF)_Prevention_Cheat_Sheet
  "Cross-site request forgery"
[forbidden header name]: https://developer.mozilla.org/en-US/docs/Glossary/Forbidden_header_name
