# Native Module 練習
React Native 0.59.5
- 使用 react-native-create-library 建立 Native Module
- 使用 Haul 測試 Native Module
- Native Modeule Sample https://github.com/FuYaoDe/MyFudToast

## 新增專案
```
$ react-native init demo
$ yarn install
$ yarn add --dev haul
$ yarn haul init
$ yarn haul start
$ react-native run-android
```

## 安裝/開發
```
$ git clone https://github.com/FuYaoDe/MyFudToast.git
$ git clone https://github.com/FuYaoDe/NativeModuleStudy.git
$ cd MyFudToast
$ yarn install 
$ yarn link # 在全域註冊 react-native-my-fud-toast，讓其他專案能 link，但是是 symlinks
$ cd ..
$ cd NativeModuleStudy
$ yarn install
$ yarn link react-native-my-fud-toast
$ yarn haul start --platform android  # 因為原生不支援 symlinks，所以用 haul 啟動 bundle server
$ react-native run-android
```

## Troubleshoot

## npm start 相關
```
NativeModuleStudy/App.js`: Module `react-native-my-fud-toast` does not exist in the Haste module map
```
因為原生不支援 symlinks，所以用改 haul 啟動

## haul 相關
```
Can't resolve 'react-hot-loader'、Can't resolve 'react-dom'
```
在 link 的專案、被 link 的專案都要  
`yarn add -D react-hot-loader react-dom`
  

```
被 link 的專案 Module not found: Error: Can't resolve 'react-native'
```
在 Module 那邊 dependencies 新增 react、react-native

  
```
啟動起來 remote JS Debugging 有問題
```
https://github.com/callstack/haul/issues/535#issuecomment-484016561


參考 https://zhuanlan.zhihu.com/p/64427727
