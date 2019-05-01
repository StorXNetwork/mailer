StorX Service Mailer
====================

Email dispatcher and templates for various StorX services.

Installation and Usage
----------------------

```
npm install storx-service-mailer --save
```

```js
var StorXMailer = require('storx-service-mailer');
var mailer = new StorXMailer({
  host: '127.0.0.1',
  port: 465,
  secure: true,
  auth: {
    user: 'username',
    pass: 'password'
  },
  from: 'hello@StorX.tech'
});

mailer.dispatch('<to_email_address>', '<template_name>', {
  template: 'variables',
  go: { in: 'here' }
}, function(err) {
  // Mail sent!
});
```

Templates
---------

To add a new email template to this package, see the `templates/` directory.
Choose a new name for the template and create 3 files:

* `templatename.subject` - Contains plain text subject text (hbs supported)
* `templatename.txt` - Contains plain text email body (hbs supported)
* `templatename.html` - Contains HTML formatted email body (hbs supported)

Once these files are added to the templates directory, you can reference them 
by `templatename` when calling `Mailer#dispatch`.

