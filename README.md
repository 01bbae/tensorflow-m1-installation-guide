# Tensorflow Installation Guide for M1 Macs

There are some quirks with tensorflow installation on M1 Macs and most places don't seem to have a correct guide on it and even Apple's own developer page has problems so here is what worked for me.

1. Go to https://developer.apple.com/metal/tensorflow-plugin/
2. Scroll down to the Get Started section and download the Conda Environment from the link.
3. Open your terminal. You should be in your root directory by default.
4. Run

```
mv ~/Downloads/Miniconda3-latest-MacOSX-arm64.sh ~
```

5. Continue with the Setup guide on the Apple developer website by running

```
bash ~/miniconda.sh -b -p $HOME/miniconda
source ~/miniconda/bin/activate
conda install -c apple tensorflow-deps
```

**_Here is where it deviates from Apple's instructions_**

If you run the command

```
python -m pip install tensorflow-macos
```

and

```
python -m pip install tensorflow-metal
```

as in the developer guide you will run into [errors](https://developer.apple.com/forums/thread/721619) later in your test script.

6. Instead, run the commands

```
python -m pip install tensorflow-macos==2.9
```

and

```
python -m pip install tensorflow-metal==0.5.0
```

7. Make sure your numpy is updated by using

```
pip install numpy --upgrade
```

8. Verify the installation worked by running the test script on the website.

## You should be set!
