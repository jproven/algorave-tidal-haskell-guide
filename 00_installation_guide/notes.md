The installation order is important for TidalCycles to work correctly. The recommended order is:

## 1. SuperCollider
    
    It’s the audio engine that makes the patterns sound.

Download it from: https://supercollider.github.io/downloads. After installing it, don’t open it yet, wait until you reach step 5.

## 2. Install Haskell and Cabal

   TidalCycles is written in Haskell and managed with Cabal, its package manager.

Currently, it’s done through GHCup (https://www.haskell.org/downloads/), which allows you to install GHC (the Haskell compiler), Cabal (the package manager), Stack (optional), and Haskell Language Server (for use in editors like VS Code or Atom).

✅ What do you need to install for TidalCycles?  
Just this:

| Tool                     | Required? | Recommended Version                                        |
|--------------------------|-----------|-------------------------------------------------------------|
| GHC (The Haskell compiler)         | ✅ Yes    | Latest stable (e.g. 9.6.4 or 9.4.x, avoid 9.12 for now if possible) |
| Cabal (The package manager)       | ✅ Yes    | 3.12.0.0 (this is the recommended one)                      |
| HLS (Haskell Language Server)     | ❌ No     | (optional, for smart editors)                               |
| Stack (optional)                  | ❌ No     | (not needed for Tidal)                                      |

Certain versions of TidalCycles aren’t fully compatible with some versions of GHC. The ones I use and know work well are **GHC 9.4.7** and **Cabal 3.8.x**.

You can easily install a specific version of GHC using `ghcup` from the terminal. Run:

```bash
ghcup install ghc 9.4.7
```

Then set it as the active version:

```bash
ghcup set ghc 9.4.7
```

And for Cabal:

```bash
ghcup install cabal 3.8.1.0
ghcup set cabal 3.8.1.0

```

## 3. Install TidalCycles

Open a terminal and run:

```bash
cabal install tidal

```

This will install the tidal package to be used inside the GHCi interpreter.

## 4. Code editor with Tidal support

Atom was very popular at one time, although it should be noted that support for it ended on December 15, 2022. Still, I’m including the repositories to get it along with the TidalCycles package, in case anyone is interested.

https://github.com/atom/atom
https://github.com/crucialfelix/atom-tidalcycles

In my opinion, the most convenient option is **VSCode**, by installing the **TidalCycles for VSCode** extension.

Once the extension is installed, **VS Code might not find Tidal’s boot file**,  
which means it can’t initialize properly.

Let’s fix that.

In VS Code, go to: **File > Preferences > Settings**

| File name       | Example path                                                         |
|-----------------|----------------------------------------------------------------------|
| `BootTidal.hs`  | `C:\Users\X\AppData\Roaming\cabal\x86_64-windows-ghc-9.6.7\tidal-1.10.0\BootTidal.hs` |

> 💡 The path will look something like this, but replace `X` with your username and adjust the GHC and tidal versions accordingly.

✅ **Verify that GHCi is working**  
Tidal runs inside **GHCi** (the Haskell interpreter), so VS Code needs to be able to find it.

Open a terminal in VS Code and type:

```bash
ghci

```

## 5. Run SuperDirt in SuperCollider

Open **SuperCollider** and run this line:

    Quarks.install("SuperDirt")

This will download and install the necessary code from the official repository. Then, restart SuperCollider.

At this point, you’ve probably installed **SuperDirt** correctly, but you still can’t use it because **SuperCollider needs to recompile the class library** before it can recognize the `SuperDirt` class.

✅ **Solution: Recompile the library and restart the server**  
    Follow these exact steps:

🔁 **Recompile the library**  
    In SuperCollider, click the top menu:

**Language > Recompile Class Library**  
    Or use the shortcut: `Ctrl + Shift + L`

Run the following:

    include("SuperDirt")
    SuperDirt.start

After completing the entire process, if everything was done correctly and is working as expected, you’ll only need to run the **second command** whenever you want to use it:

    SuperDirt.start

Now **SuperDirt should load properly** and start showing lines like:

    SuperDirt: startup done
    SuperDirt: sound library ready!
    SuperDirt: listening on port 57120

Now it’s just a matter of writing code in a `.tidal` file in VS Code and running it. This is done by selecting the text and pressing `Ctrl + Enter`.
