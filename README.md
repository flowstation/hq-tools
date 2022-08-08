# HQ Tools JavaScript SDK

The HQ Tools let you integrate easily with the services offered by Headquarters.

## Getting Started

### Load the SDK

Load the latest hq-tools SDK into your website. Find the latest version on our [HQ Tools Github page](https://github.com/flowstation/hq-tools).

```html
<script src="./hq-0.1.0.min.js"></script>
```

### Initialising the SDK

In your JavaScript initialise the HQ Tools SDK by calling the `init` function. The parameters `name`, `url` and `logoUrl` are required.

```js
window.addEventListener('DOMContentLoaded', function () {
  hq.init({
    name: 'My Web Project',
    url: 'https://mywebproject.com',
    logoUrl: 'https://mywebproject.com/img/logo.svg'
  })
})
```

## HQ Multisend

[HQ Multisend](https://app.hq.xyz/multisend) allows you to quickle distribute funds to a list of multiple recipients. Using the HQ Tools JavaScript SDKs `multisend` function you can embed a button into your website that provides a link to prefill the HQ Multisend form with a list of recipient wallets and corresponding token amounts.

![HQ Multisend Embed Button](https://github.com/flowstation/hq-tools/blob/main/docs/static/img/hq-multisend-button.png?raw=true)

To do so, the `multisend` function expects a DOM element id as `elem`, this is the element the button will be rendered in, a `purpose` describing the transaction and a `recipients` array containing objects with the details of each recipient. An optional `label` text can be passed to change the button label.

Calling the function multiple times will update the parameters.

```js
hq.multisend({
    elem: 'multisend',
    purpose: 'Distribute funds',
    label: 'Send transaction with HQ Multisend',
    recipients: [{
        address: '0xcEe6FeBe294D5591ed3ec94EBfcE35067cBA901F',
        token: 'USDT',
        amount: 0.01,
        name: 'Recipient name'
    }]
})
```
