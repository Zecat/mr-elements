# paper-toast-patterns


[Demo & Doc](http://zecat.github.io/paper-toast-patterns)


```
	bower install --save Zecat/paper-toast-patterns
```

## Factorize your paper-toasts using patterns.


First create some &lt;paper-toast&gt; as child of &lt;paper-toast-patterns&gt;, give them a 'type' 
attribute to retrieve them later and configure/style them as you please.

Exemple :

```html
  <style is="custom-style">
    paper-toast[type="warn"] {
      font-weight: bold;
      --paper-toast-color: var(--google-red-500);
    }
    paper-toast[type="info"] {
      --paper-toast-color: var(--google-blue-500);
    }
  </style>
  <paper-toast-patterns>
    <paper-toast type="warn" duration="0" text="Warning message pattern">
    </paper-toast>
    <paper-toast type="info"></paper-toast>
  </paper-toast-patterns>
```

Then, implement Zecat.PaperToastFirerBehavior in your favorite elements and use 
fireToast(type, text) method to open the matching type toast. If text param
isn't provide, the text from your 'toast pattern' will be used.

Exemple :

```html
<dom-module id="toast-sender">
  <template>
    <paper-button on-tap="sendWarn">warning</paper-button>
    <paper-button on-tap="sendInfo">info</paper-button> 
  </template>

  <script>
    Polymer({
      is: 'toast-sender',
      behaviors: [
        Zecat.PaperToastFirerBehavior
      ],
      sendWarn: function() {
        this.fireToast('warn');
      },
      sendInfo: function() {
        this.fireToast('info', 'A spermatozoid contains 37.5 mb of data.');
      }
    });
  </script>
</dom-module>
```

You can also trigger yourself the toast from anywhere by firing an event 
with this exact structure :

```js
  this.fire('iron-signal', {
    name: 'toast',
    data: {
      type: "your-type",
      text: "your-text"
    }
  });
```