
*react-websocket-flux*: Building React application with Websocket by Flux architecture.

## Install

To setup the package.

```
npm install react-websocket-flux --save
```

## Quickstart

Use react-websocket-flux to implement your React component.

```
import { WebsocketStore, WebsocketActions } from 'react-websocket-flux';

export class MyApp extends Component {
    constructor(props, context) {
        super(props, context);

        this.onMessage = this.onMessage.bind(this);
        WebsocketActions.connect(this.props.server);
    }

    componentDidMount() {
        WebsocketStore.addMessageListener(this.onMessage);
    }

    componentWillUnmount() {
        WebsocketStore.removeMessageListener(this.onMessage);      
    }

    onMessage(data) {
        this.setState(data)
    }

    render() {
        return (    
            <div>
            </div>
        );
    }
}
```

Use your React component with ```server``` props.

```
render(
	<MyApp server="wss://wot.city/object/testman/viewer" />,
    document.getElementById('content')
);
```

## Usage

How to implement your React component with react-websocket-flux.

1. Import ```WebsocketStore``` and ```WebsocketActions``` from ```react-websocket-flux```.
2. Invoke ```WebsocketActions.connect``` method to connect to Websocket server.
3. Invoke ```WebsocketStore.addMessageListener``` to register ```onMessage``` listener to Flux store.
4. Implement ```onMessage``` listener callback. For ES6, please bind ```this``` to ```onMessage```.

## License

The [MIT License](http://www.opensource.org/licenses/MIT) (MIT). See [LICENSE.md](LICENSE.md).
