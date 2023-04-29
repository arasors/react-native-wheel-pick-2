
# [react-native-wheel-pick-2](https://www.npmjs.com/package/react-native-wheel-pick-2)

This package is an updated version of [react-native-wheel-pick](https://github.com/TronNatthakorn/react-native-wheel-pick) with dependencies.

React native wheel picker for both iOS and android. (Support DatePicker)


## Preview

![](https://i.ibb.co/4W7h12M/rn-wl-pk-1-1-13.png)

## Note

- For Picker of iOS use [@react-native-picker/picker](https://github.com/react-native-picker/picker)
- For DatePicker of iOS use [@react-native-community/datetimepicker](https://github.com/react-native-datetimepicker/datetimepicker) 
- For Picker and DatePicker of Android use WheelPicker of [AigeStudio](https://github.com/AigeStudio/WheelPicker)

## How to use

React Native >= 0.60+
```
npm install react-native-wheel-pick-2 --save --legacy-peer-deps
npm install @react-native-picker/picker --save --legacy-peer-deps
npm install @react-native-community/datetimepicker --save --legacy-peer-deps
npx pod-install

npx react-native run-ios // re-build native-code
npx react-native run-android // re-build native-code for gradle
```

React Native < 0.60
```
npm install react-native-wheel-pick-2
react-native link react-native-wheel-pick-2
```
## Example code 

```jsx
import { Picker, DatePicker } from 'react-native-wheel-pick-2';

// use Picker
<Picker
  style={{ backgroundColor: '#333', width: 300, height: 215 }}
  textColor={"#f1f1f1"}
  selectedValue='item4'
  pickerData={['item1', 'item2', 'item3', 'item4', 'item5', 'item6', 'item7']}
  onValueChange={value => { console.log(value) }}
/>

// use DatePicker
<DatePicker
  style={{ backgroundColor: 'white', width: 370, height: 240 }} 
  onDateChange={date => { console.log(date) }}
/>

```
## More Example 

```jsx
// DatePicker set default select date
<DatePicker
  style={{ height: 215, width: 300 }}
  date={new Date('2018-06-27')} // Optional prop - default is Today
  onDateChange={date => { console.log(date) }}
/>

// DatePicker set min/max Date
<DatePicker
  style={{ height: 215, width: 300 }}
  minimumDate={new Date('2000-01-01')}
  maximumDate={new Date('2050-12-31')}
  onDateChange={date => { console.log(date) }}
/>

```
```jsx
// pickerData also support array of object.

// Way 1
<Picker
  selectedValue='item4'
  pickerData={['item1', 'item2', 'item3', 'item4', 'item5', 'item6', 'item7']}
  onValueChange={value => { console.log(value) }}
/>

// Optional Way 2
<Picker
  style={{ backgroundColor: 'white', width: 300, height: 215 }}
  selectedValue='5765387680'
  pickerData={[
    { value : '5765387677', label : 'item1' },
    { value : '5765387678', label : 'item2' },
    { value : '5765387679', label : 'item3' },
    { value : '5765387680', label : 'item4' },
    { value : '5765387681', label : 'item5' },
    { value : '5765387682', label : 'item6' },
    { value : '5765387683', label : 'item7' },
  ]}
  onValueChange={value => { console.log(value) }}
/>
```
```jsx
// Android Only.
// These is special props for Android. (iOS not work)
// You can also use these props for DatePicker, too.
<Picker
  textColor='red'
  textSize={20}

  selectTextColor='green'
  isShowSelectBackground={false} // Default is true
  selectBackgroundColor='#8080801A' // support HEXA color Style (#rrggbbaa)
  // (Please always set 'aa' value for transparent)
  
  isShowSelectLine={false} // Default is true
  selectLineColor='black'
  selectLineSize={6} // Default is 4
/>

// Android Only.
<DatePicker
  order='D-M-Y' // Default is M-D-Y
/>
```
## Release Note
[Android]
- Update sdk support for SDK Version 33 (Google Play need sdk version 30+)


### PROPS

| Prop          | Type                 | Default | Description                                           |
|---------------|----------------------|---------|-------------------------------------------------------|
| date          | `instanceOf(Date)`   |         | The initial date to be displayed.                     |
| maximumDate   | `instanceOf(Date)`   |         | The maximum date that can be selected.                |
| minimumDate   | `instanceOf(Date)`   |         | The minimum date that can be selected.                |
| mode          | `oneOf(['date', 'time', 'datetime'])` | 'date'  | The display mode for the date picker.                 |
| onDateChange  | `func.isRequired`    |         | Callback function to be called when the date changes. |




| Prop          | Type                 | Default   | Description                                           |
|---------------|----------------------|-----------|-------------------------------------------------------|
| textColor     | `string`             | '#333'    | The color of the text in the picker.                  |
| textSize      | `number`             | 26        | The size of the text in the picker.                   |
| itemStyle     | `object`             | null      | The style for the picker items.                       |
| onValueChange | `func.isRequired`    |           | Callback function to be called when the value changes.|
| pickerData    | `array.isRequired`   |           | The data for the picker items.                        |
| style         | `object`             | {}        | The style for the picker container.                   |
| selectedValue | `any`                | ''        | The initially selected value in the picker.           |
