# Alternative usage: styled popup

Alternatively, it is possible to use a styled popup that displays icons in the app list:

![Popup](https://i.imgflip.com/2avtml.gif)

To use the library in that way, you can import the `Popup` component:

```js
import { Popup } from 'react-native-map-link';

<Popup
    isVisible={this.state.isVisible}
    onCancelPressed={() => this.setState({ isVisible: false })}
    onAppPressed={() => this.setState({ isVisible: false })}
    onBackButtonPressed={() => this.setState({ isVisible: false })}
    modalProps={{ // you can put all modal props inside.
        animationType: 'slide' 
    }}
    options={{ /* See `showLocation` method above, this accepts the same options. */ }}
    style={{ /* Optional: you can override default style by passing your values. */ }}
/>
```

The Popup component uses <a href="https://reactnative.dev/docs/modal">react native modal</a>. So you can pass all react native modal properties inside "modalProps" to modify styling and animations.

Also, you can customize the styling of the popup by passing an object like this in the `style` prop of the `Popup` component:

```js
{
    container: {},
    itemContainer: {},
    image: {},
    itemText: {},
    headerContainer: {},
    titleText: {},
    subtitleText: {},
    cancelButtonContainer: {},
    cancelButtonText: {},
    separatorStyle: {},
    activityIndicatorContainer: {}
}
```

### Custom Header and Footer Components

You can also make use of your own Header and Footer components by adding the `customHeader` and/or `customFooter` Props to the Popup component. See the example below:

```js

renderHeader() {
  return <MyCustomHeaderComponent/>
}

renderFooter() {
  return <MyCustomFooterComponent/>
}

render() {
  return (
    <Popup
      ...
      customHeader={this.renderHeader()}
      customFooter={this.renderFooter()}
    />
  );
}

```
