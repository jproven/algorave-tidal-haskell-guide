# 🔊 SuperCollider + SuperDirt – Basic Cheat Sheet (with Haskell-style comments)

## ▶️ Boot the audio server and SuperDirt
```supercollider
s.boot;             // -- Boot the SuperCollider audio server
SuperDirt.start;    // -- Start SuperDirt (required before using TidalCycles)
```

## ⛔ Stop and free resources

```supercollider
s.quit;             // -- Quit the SuperCollider server completely
s.freeAll;          // -- Free all running synths (useful if sound is stuck)
```

## 🔁 Restart or recover

```supercollider
s.reboot;           // -- Restart the server (like a soft reboot)
```

## 🔊 Volume and meter

```supercollider
s.meter;            // -- Open volume meter (shows levels of each channel)
s.scope;            // -- Open an oscilloscope to visualize audio waveforms
```

## ⚙️ Server configuration (optional)

```supercollider
s.options.numBuffers = 1024;         // -- Increase number of audio buffers
s.options.memSize = 8192 * 16;       // -- Set memory allocation for audio
s.options.maxNodes = 1024 * 32;      // -- Allow more simultaneous synths
s.options.numOutputBusChannels = 2;  // -- Stereo output
s.options.numInputBusChannels = 2;   // -- Stereo input
```

## 📁 Load custom samples (optional)

```supercollider
SuperDirt.loadSoundFiles;           // -- Reload your samples if you added new ones
```

## 💡 Tips

```supercollider
// -- Press Ctrl + .  to stop all processes instantly (panic button)
// -- Errors will show in the post window below the editor
```