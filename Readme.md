# XR Meters

A simple example library to demonstrate how to get @music-tribe Behringer/Midas X Air XR/MR Series mixer's meter data, in Node.JS

It's useful for electron applications etc. but not intended to be used as a standalone package or repository - just something you might copy and paste bits of, or even just be inspired by.

Parameters.txt also contains all the parameters and commands for OSC with this series of Mixers, from the firmware provided by Behringer. 

# Output Format

All values are in decibels, and are signed. Minimum values tend to be around -100, max is +10 (the limit of the headroom on the device)

```
{
    '1':0.0, //channel 1 - prefade
    '2':0.0, //channel 2 - prefade
    '3':0.0, //channel 3 - prefade
    '4':0.0, //channel 4 - prefade
    '5':0.0, //channel 5 - prefade
    '6':0.0, //channel 6 - prefade
    '7':0.0, //channel 7 - prefade
    '8':0.0, //channel 8 - prefade
    '9':0.0, //channel 9 - prefade
    '10':0.0, //channel 10 - prefade
    '11':0.0, //channel 11 - prefade
    '12':0.0, //channel 12 - prefade
    '13':0.0, //channel 13 - prefade
    '14':0.0, //channel 14 - prefade
    '15':0.0, //channel 15 - prefade
    '16':0.0, //channel 16 - prefade
    'auxL':0.0, //aux in channel - prefade (left)
    'auxR':0.0, //aux in channel - prefade (right)
    'fx1PreL':0.0, //Effect prefade
    'fx1PreR':0.0,
    'fx2PreL':0.0,
    'fx2PreR':0.0,
    'fx3PreL':0.0,
    'fx3PreR':0.0,
    'fx4PreL':0.0,
    'fx4PreR':0.0,
    'bus1Pre':0.0, //Bus prefade
    'bus2Pre':0.0,
    'bus3Pre':0.0,
    'bus4Pre':0.0,
    'bus5Pre':0.0,
    'bus6Pre':0.0,
    'fx1SendPre':0.0, //Effect send prefade
    'fx2SendPre':0.0,
    'fx3SendPre':0.0,
    'fx4SendPre':0.0,
    'mainPostL':0.0, //Main mix out postfade (left)
    'mainPostR':0.0, //Main mix out postfade (right)
    'monL':0.0, //Monitor out (left)
    'monR':0.0, //Monitor out (right)
}

```

## Example Response (in Decibels)

```
{
    '1': -33.56640625,
    '2': -32.4921875,
    '3': -100.359375,
    '4': -100.359375,
    '5': -100.359375,
    '6': -100.359375,
    '7': -100.359375,
    '8': -100.359375,
    '9': -100.359375,
    '10': -100.359375,
    '11': -100.359375,
    '12': -100.359375,
    '13': -100.359375,
    '14': -100.359375,
    '15': -99.69921875,
    '16': -100.359375,
    auxL: -33.18359375,
    auxR: -32.4921875,
    fx1PreL: -128,
    fx1PreR: -128,
    fx2PreL: -110.55859375,
    fx2PreR: -112.25390625,
    fx3PreL: -128,
    fx3PreR: -128,
    fx4PreL: -128,
    fx4PreR: -128,
    bus1Pre: -128,
    bus2Pre: -128,
    bus3Pre: -128,
    bus4Pre: -128,
    bus5Pre: -128,
    bus6Pre: -128,
    fx1SendPre: -128,
    fx2SendPre: -128,
    fx3SendPre: -128,
    fx4SendPre: -128,
    mainPostL: -30.1015625,
    mainPostR: -29.875,
    monL: -30.1015625,
    monR: -29.875
}
```

## Example Response (as Percentage)

```
{
    '1': 0.6809895833333334,
    '2': 0.6619140625000001,
    '3': 0,
    '4': 0,
    '5': 0,
    '6': 0,
    '7': 0,
    '8': 0,
    '9': 0,
    '10': 0,
    '11': 0,
    '12': 0,
    '13': 0,
    '14': 0,
    '15': 0,
    '16': 0,
    auxL: 0.04233940972222222,
    auxR: 0.041026475694444446,
    fx1PreL: 0,
    fx1PreR: 0,
    fx2PreL: 0.8501302083333333,
    fx2PreR: 0.8501302083333333,
    fx3PreL: 0,
    fx3PreR: 0,
    fx4PreL: 0,
    fx4PreR: 0,
    bus1Pre: 0,
    bus2Pre: 0,
    bus3Pre: 0,
    bus4Pre: 0,
    bus5Pre: 0,
    bus6Pre: 0,
    fx1SendPre: 0,
    fx2SendPre: 0.8058593749999999,
    fx3SendPre: 0,
    fx4SendPre: 0,
    mainPostL: 0.7188802083333333,
    mainPostR: 0.6950520833333332,
    monL: 0.7188802083333333,
    monR: 0.6950520833333332
}
```

# Getting started

1. Clone the repo
1. `npm install`
1. Set the IP of the mixer in main.js (top variable in the file)
1. Choose whether to return responses in decibels or as a 0-1 percentage (second variable in file) 
1. `npm start`