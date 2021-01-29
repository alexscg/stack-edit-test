<p align="center">
  <a href="https://mds.mckinsey.com/develop/react/get-started">
    <img alt="McKinsey Design System" src="https://ddls-cdn.s3.amazonaws.com/assets/images/git/HomeImgGit.png" width="100%" />
  </a>
  <a href="https://mds.mckinsey.com/develop/react/get-started">
  </a>
</p>

Welcome to McKinsey Design System (MDS) React library of components.  This library is part of a larger design system and was built with that in mind.  Its purpose is to provide a React implementation of MDS based on the Firm's visual identity guidelines.  As such, it is geared towards implementing designs that are created using [MDS Core Library](https://mds.mckinsey.com/design/get-started), user is encouraged to use it for solutions that fit this profile.  It is also a living and evolving system that is built in an extensible and backwards-compatible manner that sees community as the main driver; your contributions are greatly anticipated!  Check out our [changelog](https://mds.mckinsey.com/develop/react/changelog) to see the evolution of the project and peek into the future on our [roadmap](https://mds.mckinsey.com/develop/react/get-started#our-roadmap).

#### Getting Started
If you are just getting started with MDS React Library please visit our [getting started page](https://mds.mckinsey.com/develop/react/get-started/).  It has all the information you need to get up to speed quickly and start coding.

#### Installation
Configure Firm's on-prem jFrog artifactory to install MDS React library.  You will need a active account to get access.
```sh
npm config set @mds:registry https://artifacts.intranet.mckinsey.com/artifactory/api/npm/mds-npm/
```
Install the MDS React library.
```javascript
npm install --save @mds/mds-reactjs-library
```

#### Importing components

Now that MDS React library is a dependency you can import MDS components in your React code.

```jsx
import { Button } from '@mds/mds-reactjs-library';
```

#### Alternative installation methods

Did the installation steps listed above not work in your project? Don't worry we have other means to install!  Please refer to one of the following tutorials which contain step-by-step instructions based on your use case.

- [NPM installation](https://mds.mckinsey.com/develop/react/tutorial/npm)
- [create-react-app](https://mds.mckinsey.com/develop/react/tutorial/create-react-app)

#### Get in touch with us
As we start to ramp up, be on the lookout for our email newsletter about  latest developments, releases and goings-on.  Our portal is the best place to get information fast.  We also make announcements on our Slack channels where you can ask questions, help others and provide your expertise.  We encourage you to reach out to our team for questions about integration, [contribution](https://mds.mckinsey.com/develop/contribution) and anything else at [#mds-tech](https://mck-td.slack.com/archives/CN7ALAXNZ) or [#mds-community](https://mck-td.slack.com/archives/CLWC6P8H0).

Here is our [roadmap](https://mds.mckinsey.com/develop/react/get-started#our-roadmap) for the near future and .



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
eyJoaXN0b3J5IjpbLTIwOTAwMDY0MDcsLTc1MTg4ODA2Nyw2Nj
YwMTk2NzgsLTg4NjU4NDcwNCwtMzg0NzM5NDIxLDg1NTE0ODM5
MiwxMjk1NDYwODgsLTE0NTUxMDA1OTQsMTQxNjY4NjMzMSwtMT
A1MDExMTA4NV19
-->