# React-native-connectivity-status

forked from [nearit/react-native-connectivity-status](https://github.com/mitigate-dev/react-native-connectivity-status)
to fix build issues on newer React Native. Tested on 0.73.6

===================================

> A [React Native](https://facebook.github.io/react-native/) module to check Bluetooth and Location status on Android and iOS

## Installation

```
yarn add mitigate-dev/react-native-connectivity-status
```

## Usage

### Check Status

Interactively check Location Services and Bluetooth status

```js
import ConnectivityManager from "react-native-connectivity-status";

// Check if Location Services are enabled
const locationServicesAvailable = await ConnectivityManager.areLocationServicesEnabled();
```

Subscribe to updates

```js
import ConnectivityManager from 'react-native-connectivity-status'

const connectivityStatusSubscription = ConnectivityManager.addStatusListener(({ eventType, status }) => {
	switch (eventType) {
		case 'bluetooth':
					console.log(`Bluetooth is ${status ? 'ON' : 'OFF'}`)
				break
		case 'location':
					console.log(`Location Services are ${status ? 'AVAILABLE' : 'NOT available'}`)
				break
	}
})
...
// Remeber to unsubscribe from connectivity status events
connectivityStatusSubscription.remove()
```
