# AsyncStorage Retrieval Immediately After Storage Returns Null

This repository demonstrates a bug in React Native's AsyncStorage where retrieving data immediately after storage results in null or undefined being returned, despite successful data persistence.

## Bug Description
The issue occurs when attempting to retrieve data from AsyncStorage immediately after storing it using `setItem`.  The `getItem` call returns null or undefined, even though the data was written successfully (verified through later retrieval or database inspection).

## Reproduction
1. Clone this repository.
2. Run the app on an Android or iOS emulator/device.
3. Observe the console output.  It will show the inconsistent retrieval behavior.

## Solution
The solution involves introducing a small delay using `setTimeout` before attempting to retrieve the newly stored data. This allows AsyncStorage sufficient time to complete the write operation.

## Contributing
Contributions are welcome!  Please open an issue or submit a pull request.