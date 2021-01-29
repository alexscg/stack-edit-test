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

function Demo() {
  return (
   <Button>Primary Button</Button>
  );
}

export default Demo;
```
> NOTE: You should use ThemeProvider component as shown in [examples](https://mds.mckinsey.com/develop/react/components/button) on MDS Portal.  

#### Alternative installation methods

Did the installation steps listed above not work in your project? Don't worry we have other means to install!  Please refer to one of the following tutorials which contain step-by-step instructions based on your use case.

- [NPM installation](https://mds.mckinsey.com/develop/react/tutorial/npm)
- [create-react-app](https://mds.mckinsey.com/develop/react/tutorial/create-react-app)

#### Get in touch with us
As we start to ramp up, be on the lookout for our email newsletter about  latest developments, releases and goings-on.  Our portal is the best place to get information fast.  We also make announcements on our Slack channels where you can ask questions, help others and provide your expertise.  We encourage you to reach out to our team for questions about integration, [contribution](https://mds.mckinsey.com/develop/contribution) and anything else at [#mds-tech](https://mck-td.slack.com/archives/CN7ALAXNZ) or [#mds-community](https://mck-td.slack.com/archives/CLWC6P8H0).

Here is our [roadmap](https://mds.mckinsey.com/develop/react/get-started#our-roadmap) for the near future and a [changelog](https://mds.mckinsey.com/develop/react/changelog) of the close past.


#### License
 
##### CONFIDENTIAL AND PROPRIETARY
This software is confidential and for Firm internal use only.<br/>
Any use or disclosure of this software without specific permission of McKinsey & Company is strictly prohibited.<br/>
All rights reserved.
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTEzMjI5NTUwMDIsMTQ4OTkxNzg2MCwtNz
UxODg4MDY3LDY2NjAxOTY3OCwtODg2NTg0NzA0LC0zODQ3Mzk0
MjEsODU1MTQ4MzkyLDEyOTU0NjA4OCwtMTQ1NTEwMDU5NCwxND
E2Njg2MzMxLC0xMDUwMTExMDg1XX0=
-->