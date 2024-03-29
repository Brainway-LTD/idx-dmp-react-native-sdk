# react-native-idx-dmp-sdk

IDX DMP react-native SDK

## Installation

```sh
yarn add react-native-idx-dmp-sdk
```

## Usage

```js
import {
  initSdk,
  sendEvent,
  getUserId,
  getDefinitionIds,
  resetUserState,
} from 'react-native-idx-dmp-sdk';

// ...

const PROVIDER_ID = '00000000-0000-0000-0000-000000000000';

// Init sdk before any other events
initSdk(PROVIDER_ID, 'My app name').then(() => {
  // setIsReady
});


// Prepare event data
const pageState = {
  url: '',
  title: '',
  domain: '',
  author: '',
  category: '',
  description: '',
  tags: 'tag1,tag2,tag3',
}

sendEvent(pageState).then(() => {
  // event is completed
  const audiences = getDefinitionIds() // return calculated audiences
  const userId = getUserId() // return current user id
  const adRequstData = {
    customData: `dxseg=${audiences}&dxu=${userId}&permutive=${userId}`,
  }
  
})
```

## License

MIT
