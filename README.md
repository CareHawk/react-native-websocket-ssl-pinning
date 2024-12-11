# react-native-websocket-ssl-pinning

Creates a secure WebSocket connection using ssl-pinning technique.

## Installation

Add the following line in the `"dependencies"` field inside `package.json` of the project:
```sh
"react-native-websocket-ssl-pinning": "git+ssh://git@github.com:CareHawk/react-native-websocket-ssl-pinning.git#master",
```

## Usage

Create the connection
```js
import { fetch } from 'react-native-websocket-ssl-pinning';

try{
  const response = await fetch(`wss://${serverip}/`, {
	method: 'GET',
	timeoutInterval: 10000, // Request timeout
	sslPinning: {
	  certs: ['rootCA_public'],
	},
  });
  
  if (response.code === 101) {
	console.log(
	  'Switching protocols. Starting secure web socket connection...',
	);

	socketOpen()
  }
} catch(e) {
  console.error(e);
}
```

*TODO: finish usage*


## Contributing

See the [contributing guide](CONTRIBUTING.md) to learn how to contribute to the repository and the development workflow.

## License

MIT

---

Made with [create-react-native-library](https://github.com/callstack/react-native-builder-bob)
