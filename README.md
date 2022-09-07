# react-native-modal-custom

Cross platform ActionSheet. This component implements a custom ActionSheet and provides the same way to drawing it on the defferent platforms(iOS and Android). Actually, In order to keep the best effect, it still uses the ActionSheetIOS on iOS.

<table>
  <tbody>
    <tr>
      <td align="center" valign="top">
        <img width="210" src="./docs/ios-custom.png">
      </td>
      <td align="center" valign="top">
        <img width="210" src="./docs/ios-native.png">
      </td>
    </tr>
  </tbody>
</table>

## Install

```
npm install react-native-modal-custom --save
```

## Usage

```js
import ActionSheet from "react-native-modal-custom";

class Demo extends React.Component {
  showActionSheet = () => {
    this.ActionSheet.show();
  };
  render() {
    return (
      <View>
        <Text onPress={this.showActionSheet}>Open ActionSheet</Text>
        <ActionSheet
          ref={(o) => (this.ActionSheet = o)}
          title={"Which one do you like ?"}
          options={["Apple", "Banana", "cancel"]}
          cancelButtonIndex={2}
          destructiveButtonIndex={1}
          onPress={(index) => {
            /* do something */
          }}
        />
      </View>
    );
  }
}
```

### Use ActionSheetCustom directly

so you can customize option and title

```js
import { ActionSheetCustom as ActionSheet } from "react-native-modal-custom";

const options = [
  "Cancel",
  "Apple",
  <Text style={{ color: "yellow" }}>Banana</Text>,
  "Watermelon",
  <Text style={{ color: "red" }}>Durian</Text>,
];

class Demo extends React.Component {
  showActionSheet = () => {
    this.ActionSheet.show();
  };
  render() {
    return (
      <View>
        <Text onPress={this.showActionSheet}>Open ActionSheet</Text>
        <ActionSheet
          ref={(o) => (this.ActionSheet = o)}
          title={
            <Text style={{ color: "#000", fontSize: 18 }}>
              Which one do you like?
            </Text>
          }
          options={options}
          cancelButtonIndex={0}
          destructiveButtonIndex={4}
          onPress={(index) => {
            /* do something */
          }}
        />
      </View>
    );
  }
}
```

### How to redesign style ?

The style of ActionSheet is defined in [src/styles.js](https://github.com/vnphu/react-native-modal-custom/blob/master/src/styles.js).

```javascript
// example

const styles = {
  titleBox: {
    background: 'pink'
  },
  titleText: {
    fontSize: 16,
    color: '#000'
  }
}

<ActionSheet
  ...
  styles={styles}
/>
```

## Props

https://github.com/beefe/react-native-modal-custom/blob/master/src/options.js

<table>
    <tr>
        <th>Prop name</th>
        <th>Description</th>
        <th>Type</th>
        <th>Default</th>
    </tr>
    <tr>
        <td>title</td>
        <td></td>
        <td>PropTypes.string or PropTypes.element</td>
        <td></td>
    </tr>
    <tr>
        <td>message</td>
        <td></td>
        <td>PropTypes.string or PropTypes.element</td>
        <td></td>
    </tr>
    <tr>
        <td>options</td>
        <td></td>
        <td>PropTypes.arrayOf([PropTypes.string, PropTypes.element])</td>
        <td></td>
    </tr>
    <tr>
        <td>tintColor</td>
        <td></td>
        <td>PropTypes.string</td>
        <td></td>
    </tr>
    <tr>
        <td>cancelButtonIndex</td>
        <td></td>
        <td>PropTypes.number</td>
        <td></td>
    </tr>
    <tr>
        <td>destructiveButtonIndex</td>
        <td></td>
        <td>PropTypes.number</td>
        <td></td>
    </tr>
    <tr>
        <td>onPress</td>
        <td></td>
        <td>PropTypes.func</td>
        <td>(index) => {}</td>
    </tr>
    <tr>
        <td>styles</td>
        <td>only for ActionSheetCustom</td>
        <td></td>
        <td>{}</td>
    </tr>
</table>
