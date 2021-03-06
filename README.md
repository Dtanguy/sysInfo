# sys-info

pack up of different call for get system data.

## Install
```
npm i "git+https://github.com/Dtanguy/sys-info.git" --save
```

https://www.npmjs.com/package/usb
Libusb is included as a submodule. On Linux, you'll need libudev to build libusb. On Ubuntu/Debian: sudo apt-get install build-essential libudev-dev

## Usage

You can put an option parameter in init() for choice what to enable/disable.
By default everything is enabled, and in case of error the lib automaticaly disable.

```js
var option = {
	cpu	: true,
	ram	: true,
	ping	: true,
	temp	: true,
	os	: true,
	usb	: true,
	disk	: true,
	network	: true,
	wifi	: true,
	modem	: true,
	serial	: true,
	android	: true,
	gps	: true		
};
```

Set the loop and the callback :
freq is between 500 and 60000 ms for monitoring
1000 and 600000 ms for hardware

```js
sysInfo.setFreqMonito(freq, callback);
sysInfo.setFreqHard(freq, callback);
```

Full example :

```js
var sysInfo = require('sysInfo');
sysInfo.init();

sysInfo.setFreqMonito(1000, function(data){
	console.log(data);
});

sysInfo.setFreqHard(60000, function(data){
	console.log(data);
});
```
