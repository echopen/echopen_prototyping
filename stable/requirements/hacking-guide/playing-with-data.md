# \[Warning\] this is related to the old 2.0. version, which is not already tagged, and you can refer to it @ commit [6f30557](https://github.com/echopen/PRJ-medtec_androidapp/commit/6f30557e4331807133075b665c34f0f870a81726) 

# Playing and Testing Data 

A lots of tools enable you to test and play with the data :

## Some generalities

The app let you get data via `TCP` or `UDP` protocol. By default, the system works with `TCP` protocol. To test `UDP` data you can switch to [redpitaya\_udp\_data](https://github.com/echopen/PRJ-medtec_androidapp/tree/redpitaya_udp_data) branch.   
  @todo : ~~create a developer mode, first screen app will then let you change the protocol~~\(done\) and set up the rights hardware constants \(number of lines, number of samples...\).

Constants are set in the `Constants` class in the `utils` package. The critical ones are : `PreProcParam.NUM_LINES` and `PreProcParam.NUM_SAMPLES`, that corresponds to the number of lines and the number of samples the hardware is acquiring.

If you want to simulate `TCP` data transfer, you can put in the `doInBackground` method of the `ProcessTCPTask` some lines as :

```while\(true\){
              int num_lines = Constants.PreProcParam.NUM_LINES;
              int num_samples = Constants.PreProcParam.NUM_SAMPLES;
              byte[] message = new byte[num_lines * num_samples];

              for (int i = 0; i < num_lines; i++) {
                  for (int j = 0; j < num_samples; j++) {
                          message[i*rows +j] = (byte) / the pixel data you want from à to 255 /;
                  }
              }
              ScanConversion scnConv = ScanConversion.getInstance(message);
              scnConv0.setTcpData();
              refreshUI(scnConv);
          }
```

```
(don't forget to comment the piece of code dealing with sockets !)
```

## Simulating real data

You'll find in the [kit-soft](https://github.com/benchoufi/formally_known_as_kit-soft) repo, you'll find some real data file [raw\_data.txt](https://github.com/benchoufi/formally_known_as_kit-soft/blob/master/data/raw_data.txt) that was output by our hardware suite.

In this repo, you'll find all the tools to install on your local a `UDP` server that can simulate a real time data coming from our hardware.

_Simulating fake but medical data_

You can get fake data either

1. from the [kit-soft](https://github.com/benchoufi/formally_known_as_kit-soft) repo, where you'll find some real data file [raw\_data.txt](https://github.com/benchoufi/formally_known_as_kit-soft/blob/master/data/raw_data.txt) that was output by our hardware suite. In this repo, you'll find all the tools to install on your local a `UDP` server that can simulate a real time data coming from our hardware.
2. from the `phantom` directory in the [Android App](https://github.com/echopen/PRJ-medtec_androidapp/). You'll find in `phantom/img_kydney.txt` and `phantom/img_obs.txt` the data that is output from the Hardware. The goal is to build and obtain from each of these double arrays the images stored respectively as `phantom/img_kydney.bmp` and `phantom/img_obs.bmp`.

** Remark : you'll have to adapt the following constants, set in the **`utils/Constants`** class, to  **`PreProcParam.NUM_LINES = 50`** and **`PreProcParam.NUM_SAMPLES`** to respectively 9270 for **`phantom/img_kydney.txt`** and 10261 for **`phantom/img_obs.txt`** **

The image `img_kydney.bmp` is more realistic than `img_obs.bmp`.

![alt tag](http://wiki.echopen.org/images/e/e1/Image_kydney.png)  
  ![alt tag](http://wiki.echopen.org/images/0/0a/Image_obs.png)

## Simulating data with a plain `JAVA` app

In the `phantom/test_data` directory, you'll find a plain `JAVA` app that lets you test and taste the data without the hassle of bothering with `Android` configuration and other heaviness.

`phantom/img_kydney.txt` and `phantom/img_obs.txt` corresponds to the raw signal that needs to be filtered. They serve as basis for the envelope detection from which pixels intensity are deduced. ** The resulting pixel file sits in **`data_kydney.csv`

In the phantom folder, there are some java classes that are meant to ran outside of android. This is useful for testing and improving the , without the hassle of running an android emulator.

** Remark : you'll have to adapt the following constants, set in the **`utils/Constants`** class, to  **`PreProcParam.NUM_LINES = 120`** and **`PreProcParam.NUM_SAMPLES = 511`

