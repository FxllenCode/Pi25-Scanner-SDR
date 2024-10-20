# Pi25-Scanner-SDR
<!-- <div align="center"> -->

![GitHub Sponsors](https://img.shields.io/github/sponsors/fxllencode?logo=github&label=Sponsor%20this%20project!) ![GitHub Repo stars](https://img.shields.io/github/stars/fxllencode/Pi25-Scanner-SDR)

<!-- </div> -->

**🚨Listen to local Police, Fire, EMS, and other digital radio communcations - with Pi!🚨**

![Pi25-Scanner-SDR](https://github.com/FxllenCode/Pi25-Scanner-SDR/blob/main/images/PXL_20240711_165216659.jpg)


⭐ Star this project if you found it helpful!

☕ *[Like this project? Buy me a coffee!](https://github.com/sponsors/FxllenCode?frequency=one-time&sponsor=FxllenCode)*




## 📚 Table of Contents

*Ready to get started? Check out the [Wiki](https://github.com/FxllenCode/Pi25-Scanner-SDR/wiki/Step-0) for a full guide on how to build the scanner!*

## 🚀 Introduction

Pi25-Scanner-SDR is a project that allows you to listen to local Police, Fire, EMS, and other digital radio communications using a Raspberry Pi and an SDR (Software Defined Radio) dongle. This project uses a multitude of different software and hardware to create a physical scanner that can listen to digital radio communications. This project is perfect for those who are interested in digital radio, or for those who want to listen to local emergency services. The end result can also be accessed over the internet, allowing you to listen to your scanner from anywhere in the world, like shown below:

https://fultonscanner.com/

The project is much more affordable scanner than buying an SDS100/200 (the only scanner comparable in features and audio quality) and is a fun project to build and learn about digital radio communications. This repository not only includes all of the instructions in the wiki, but also custom scripts that I have written to make the scanner more user-friendly and easier to use. I also provide the steps to ensuring the project is possible, and the equipment you need to buy to get started. The scanner costs about $260-$360 to build, compared to the SDS100/200 which costs $650-$700. The scanner is also much more customizable and can be upgraded in the future with better dongles to listen to more systems. 

**⚠️ DO NOT PURCHASE PRODUCTS UNTIL YOU'VE READ THROUGH THE *ENTIRE* TUTORIAL AND CONFIRMED THAT YOUR LOCAL SYSTEMS ARE COMPATIBLE! ⚠️**

## 🔧 Software Stack

The software stack for this project is as follows:
- **[rtl-sdr](https://osmocom.org/projects/rtl-sdr/wiki)** - Software used to interface with the SDR dongle.
- **[gnuradio](https://gnuradio.org)** - Core backend software for SDR radio functionality. 
- **[gqrx](https://github.com/gqrx-sdr/gqrx)** - GUI used to help configure the SDR dongle and find correct settings for trunk-recorder.
- **[trunk-recorder](https://github.com/robotastic/trunk-recorder)** - Demodulates and records P25 radio traffic. Used to record the audio from the SDR dongle. This is the primary software that allows the scanner to work.
- **[rdio-scanner](https://github.com/chuot/rdio-scanner)** - Web interface for trunk-recorder. Used to create the web interface show on the scanner's screen. Can also be accessed over the internet.
- **[cloudflared](https://github.com/cloudflare/cloudflared) (Optional)** - Used to create a secure tunnel to access the scanner over the internet. This is optional, but recommended if you want to access the scanner from anywhere in the world.

The "order" of the software and how it is used is as follows:

1. **rtl-sdr** - This is how the dongle actually works, hence why it is called an RTL-SDR dongle. Also used for initial setup of the dongle and allows it to work when plugged into the Pi.
2. **gqrx** - Used to find the correct gain and PPM settings for the dongle. This is important to ensure that the scanner can pick up the radio signals correctly. This allows also us to confirm the signals exist by finding the control channel.
3. **gnu-radio** - Not directly used, but is the backend for trunk-recorder and gqrx. This is the core software that allows the SDR dongle to work.
4. **trunk-recorder** - This is the primary software that allows the scanner to work. It records the audio from the SDR dongle and demodulates the P25 radio traffic. This is the "heart" of the project. 
5. **rdio-scanner** - This is feed the audio from trunk-recorder, and allows us to actually listen to the audio as well as sort the audio into different talkgroups. This is the web interface that is shown on the scanner's screen.


## 📦 Hardware Requirements

**Exact hardware requirements can be found in the wiki.**

- **Raspberry Pi 5** - Used to run the software and host the scanner. The Pi 5 is recommended for the best performance. This project can work on the Pi 4, but for larger and busier systems it may run out of processing power. 
- **RTL-SDR V3** - Used to pick up the radio signals. The RTL-SDR V3 is recommended for the best performance-to-power ratio. Pretty much any derivative of this dongle will work, or even other SDRs such as an Airspy. <u>**NOTE: READ THE WIKI REGARDING THE AMOUNT OF DONGLES YOU NEED TO BUY! THIS IS *VERY* IMPORTANT!**</u>
- **SD Card** - Used to store the operating system and software. A 128GB card is recommended, but a 64GB card will work.
- **Screen** - Not required, but a very cool addition to the scanner. Any screen will work, but I would recommend a 7" screen. Touchscreen is highly recommended. Ensure that the screen has a speaker built in, or you will need to buy a separate speaker. 

**All of my hardware recommendations can be found in the wiki.**

## ✨ Acknowledgements

- **[robotastic](https://github.com/robotastic)** - Creator of trunk-recorder. Amazing software that is the only reason this is even possible!
- **[Radio Reference](https://www.radioreference.com/)** - Great resource for finding local radio systems and frequencies.
- **[trunk-recorder Discord](https://discord.gg/axbxsbsMdS)** - Great community that helped me get this project up and running. Highly recommend joining if you have any questions about trunk-recorder.
- **[fekie](https://github.com/fekie)** - Helped me decide to put this in writing and logic checking everything.