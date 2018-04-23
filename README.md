# react_native_windows_failed_build_wpf

## How to reproduce a bug from scratch
1. `react-native init react_native_windows_failed_build_wpf`
1. `yarn add rnpm-plugin-windows --dev`
1. Change `package.json` to use the version `"4.0.0"` of `babel-preset-react-native` instead of "5.0.0" to avoid errors (this problem seems not related to `react-native-windows`).
1. `react-native windows`
1. Confirm a UWP app works via `react-native run-windows`
1. Confirm we can build a UWP app via `react-native bundle --platform windows --entry-file index.js --bundle-output windows\react_native_windows_failed_build_wpf\ReactAssets\index.windows.bundle --assets-dest windows\react_native_windows_failed_build_wpf\ReactAssets`
1. `react-native wpf`
1. Confirm a WPF app *DOES NOT* works via `react-native run-wpf`
1. Open and compile `wpf\react_native_windows_failed_build_wpf.sln` to fix compile errors.
1. Confirm a WPF app works via `react-native run-wpf`
1. Confirm we *CANNOT* build a WPF app via `react-native bundle --platform wpf --entry-file index.js --bundle-output wpf\react_native_windows_failed_build_wpf\ReactAssets\index.wpf.bundle --assets-dest wpf\react_native_windows_failed_build_wpf\ReactAssets`
