# 🎛️ TidalCycles – Live Coding Cheat Sheet (Performance-Focused)

## 🔇 Global & Channel Control

```haskell
hush         -- Silence everything (all channels)
mute 1       -- Mute channel d1
unmute 1     -- Unmute channel d1
solo 1       -- Solo channel d1
unsolo       -- Remove solo

```

## 🔁 Cycle & Tempo

```haskell
resetCycles  -- Reset the cycle counter to 0
setcps 1.0   -- Set tempo (cycles per second)
cps          -- Check current tempo

```

## 🛠 Reload & Clear

```haskell
:reload      -- Reload Tidal (clears all patterns and fixes errors)
```

## ▶️ Channel Playback & Silence

```haskell
d1 $ sound "bd*4"      -- Start pattern in d1
d1 silence             -- Stop channel d1
```

## 🎶 Timing & Swing

```haskell
setcps 0.9                                     -- Set a slightly slower tempo
d1 $ sound "bd" # swingBy 0.25 # swing 0.3     -- Apply swing timing to pattern
```

## 🎚 Live Effects

```haskell
d1 $ sound "bd" # gain 0.8                     -- Lower the volume
d1 $ sound "sn" # pan 0.5                      -- Center-right stereo panning
d1 $ sound "arpy" # speed 2                    -- Play sample at double speed
d1 $ sound "arpy" # delay 0.5                  -- Add delay/echo effect
```

## 🎲 Randomness

```haskell
d1 $ sound (choose ["bd", "sn", "cp"])         -- Randomly select from given samples
rand 1                                          -- Random float between 0 and 1
irand 4                                         -- Random int between 0 and 3
cutrand 3                                       -- Random cut group between samples
```

## 🔊 One-shot samples

```haskell
once $ sound "cp"         -- Trigger a one-time snare sound
```