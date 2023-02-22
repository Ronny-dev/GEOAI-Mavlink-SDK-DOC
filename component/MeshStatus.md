### Documentation

#### `private int earfcn`

frequency point type, show path loss value. default value[0, 191], err:32767

#### `private int rsrp`

RSRP [dBm]. default value[-141, -44], err:32767

#### `private int snr`

SNR [dBm]. default value[-50, +50], err:32767

#### `private int distance`

point to point distance [M], value[0, +]

#### `private String txPower`

transport power for module [dBm]

#### `private int cqi`

channel quality information, value[0, 15]

#### `private int maxSnr`

max snr in 10000ms, value[-40, +40]

#### `private int minSnr`

min snr in 10000ms, value[-40, +40]

#### `private int signalQuality`

quality for wireless, value[0, 100]. by default, 0 expression loss signal.