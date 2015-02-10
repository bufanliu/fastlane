<h3 align="center">
  <a href="https://github.com/KrauseFx/fastlane">
    <img src="assets/fastlane.png" width="150" />
    <br />
    fastlane
  </a>
</h3>
<p align="center">
  <a href="https://github.com/KrauseFx/deliver">deliver</a> &bull; 
  <a href="https://github.com/KrauseFx/snapshot">snapshot</a> &bull; 
  <a href="https://github.com/KrauseFx/frameit">frameit</a> &bull; 
  <a href="https://github.com/KrauseFx/pem">PEM</a> &bull; 
  <a href="https://github.com/KrauseFx/sigh">sigh</a> &bull; 
  <a href="https://github.com/KrauseFx/produce">produce</a> &bull;
  <b>cert</b>
</p>
-------

<p align="center">
    <img src="assets/cert.png">
</p>

cert - Create new iOS code signing certificates
============

[![Twitter: @KauseFx](https://img.shields.io/badge/contact-@KrauseFx-blue.svg?style=flat)](https://twitter.com/KrauseFx)
[![License](http://img.shields.io/badge/license-MIT-green.svg?style=flat)](https://github.com/KrauseFx/cert/blob/master/LICENSE)
[![Gem](https://img.shields.io/gem/v/cert.svg?style=flat)](http://rubygems.org/gems/cert)

###### Create new iOS code signing certificates from the command line. 

##### This tool was sponsored by [AppInstitute](http://appinstitute.co.uk/).

Get in contact with the developer on Twitter: [@KrauseFx](https://twitter.com/KrauseFx)

-------
<p align="center">
    <a href="#installation">Installation</a> &bull; 
    <a href="#usage">Usage</a> &bull; 
    <a href="#how-does-it-work">How does it work?</a> &bull; 
    <a href="#tips">Tips</a> &bull; 
    <a href="#need-help">Need help?</a>
</p>

-------

<h5 align="center"><code>cert</code> is part of <a href="http://fastlane.tools">fastlane</a>: connect all deployment tools into one streamlined workflow.</h5>



# Installation
    sudo gem install cert

Make sure, you have the latest version of the Xcode command line tools installed:

    xcode-select --install

# Usage

    cert

This does the following:

Check if any of the available signing certificates is installed.  

Only if a new certificate needs to be created:

- Create a new private key
- Create a new signing request
- Generate, downloads and installs the certificate
- Import all the generated files into your Keychain


```cert``` will never revoke your existing certificates. 

You can pass parameters like this:

    cert -u cert@krausefx.com


## Environment Variables
In case you prefer environment variables:

- ```CERT_USERNAME```
- ```CERT_TEAM_ID```
- ```CERT_KEYCHAIN```

# How does it work?

- `cert` accesses the ```iOS Dev Center``` to create or download your certificate. See: [developer_center.rb](https://github.com/KrauseFx/cert/blob/master/lib/cert/developer_center.rb).
- The ```.certSigningRequest``` file will be generated in [signing_request.rb](https://github.com/KrauseFx/cert/blob/master/lib/cert/signing_request.rb)


## How is my password stored?
```cert``` uses the [password manager](https://github.com/KrauseFx/CredentialsManager) from `fastlane`. Take a look the [CredentialsManager README](https://github.com/KrauseFx/CredentialsManager) for more information.

# Tips

## [`fastlane`](http://fastlane.tools) Toolchain

- [`fastlane`](http://fastlane.tools): Connect all deployment tools into one streamlined workflow
- [`deliver`](https://github.com/KrauseFx/deliver): Upload screenshots, metadata and your app to the App Store using a single command
- [`snapshot`](https://github.com/KrauseFx/snapshot): Automate taking localized screenshots of your iOS app on every device
- [`frameit`](https://github.com/KrauseFx/frameit): Quickly put your screenshots into the right device frames
- [`PEM`](https://github.com/KrauseFx/pem): Automatically generate and renew your push notification profiles
- [`sigh`](https://github.com/KrauseFx/sigh): Because you would rather spend your time building stuff than fighting provisioning
- [`produce`](https://github.com/KrauseFx/produce): Create new iOS apps on iTunes Connect and Dev Portal using the command line

## Use the 'Provisioning Quicklook plugin'
Download and install the [Provisioning Plugin](https://github.com/chockenberry/Provisioning).

It will show you the ```cert``` files like this: 
![assets/QuickLookScreenshot.png](assets/QuickLookScreenshot.png)


# Need help?
- If there is a technical problem with ```cert```, submit an issue.
- I'm available for contract work - drop me an email: cert@krausefx.com

# License
This project is licensed under the terms of the MIT license. See the LICENSE file.

# Contributing

1. Create an issue to discuss about your idea
2. Fork it (https://github.com/KrauseFx/cert/fork)
3. Create your feature branch (`git checkout -b my-new-feature`)
4. Commit your changes (`git commit -am 'Add some feature'`)
5. Push to the branch (`git push origin my-new-feature`)
6. Create a new Pull Request
