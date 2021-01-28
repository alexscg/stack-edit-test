<p align="center">
  <a href="https://mds.mckinsey.com/develop/react/get-started">
    <img alt="McKinsey Design System" src="https://ddls-cdn.s3.amazonaws.com/assets/images/git/HomeImgGit.png" width="100%" />
  </a>
  <a href="https://mds.mckinsey.com/develop/react/get-started">
  </a>
</p>


#### Installation

Configure Firm's on-prem jFrog artifactory to install the MDS React library.
```sh
npm config set @mds:registry https://artifacts.intranet.mckinsey.com/artifactory/api/npm/mds-npm/
```

<br />

Now, let's install the MDS React library.
```javascript
npm install --save @mds/mds-reactjs-library
```

#### Importing components

<br /> 

You've successfully installed the MDS React library. You may now import MDS components in your React code.

```jsx
import { Button } from '@mds/mds-reactjs-library';
```

#### Alternative installation methods

<br />

Did the installation steps listed above not suit your project's needs? Don't worry we have other means to install our library. 

<br />

Please refer to one of the following tutorials which contain step-by-step instructions based on your use case.

- [NPM installation](https://mds.mckinsey.com/develop/react/tutorial/npm)
- [create-react-app](https://mds.mckinsey.com/develop/react/tutorial/create-react-app)

#### Our Roadmap

  As we start to ramp up, be on the lookout for our email newsletter about
  latest developments, releases and goings-on. We will also make announcements
  on our Slack channels where you can ask questions, help others and provide
  your expertise. As the Portal comes more fully online it will be the first
  place to go look for resources for your project. In the beginning you might
  not always find exactly what you are looking for. We encourage you to reach
  out to our team so as to evaluate whether to extend current resource to fit
  your needs or to contribute a new one so the next time it will be found. Here
  is our [roadmap](https://mds.mckinsey.com/develop/react/get-started#our-roadmap) for this year.



#### Contribution

- You can reach out to us via our slack channel <PortalLink target="_blank" href="https://mck-td.slack.com/archives/CN7ALAXNZ">#mds-tech</PortalLink>.
- You can also email us if you have any questions [MDS](mailto:mds@mckinsey.com?subject=[MDS]%20React%20Contribution%20Inquiry)
- How to [contribute](https://mds.mckinsey.com/develop/contribution)

#### Changelog

Checkout our [changelog](https://mds.mckinsey.com/develop/react/changelog) to know what`s changed.

#### License
 
##### CONFIDENTIAL AND PROPRIETARY.<h4>
 This software is confidential and for internal use only.<br/>
 Any use or disclosure of this software without specific permission of McKinsey & Company is strictly prohibited.<br/>
 All rights reserved.


<!--
# Multi-repository for mds-reactjs-library
 
##Lerna 
https://github.com/lerna/lerna
https://lerna.js.org/

##Step By Step
1. run ```npm i``` in mds-reactjs-library 
2. run ```npm run bootstrap``` (command will install npm packages into modules in "modules" folder and will create links in node_modules)

## Publish
We are publishing following packages:
- mds-docs - @mds/mds-reactjs-library-docs
- mds-library - @mds/mds-reactjs-library

To publish packages you should run ```lerna publish```.

--->
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTIwNzYyMzAyNzYsLTE0NTUxMDA1OTQsMT
QxNjY4NjMzMSwtMTA1MDExMTA4NV19
-->