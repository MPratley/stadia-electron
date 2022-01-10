# WIP attempt at getting a 0 effort vaapi-supporting stadia

# About

Stadia application in a VA-API enabled electron wrapper.

If you're currently having bad stutter when trying stadia on linux, this might be what you're looking for!

# Installation

As of now, best to use the development instructions below. Once this is confirmed to be stable I'll make some release candidates.

# Requirements

You'll need `vaapi` support. Setting this up will vary by driver and by distro. 

To test that `vaapi` is supported you can run `vainfo`. 
Here is an example output on *fedora 35* for `vainfo` (provided by `libva-utils`):

```
vainfo: VA-API version: 1.13 (libva 2.13.0)
vainfo: Driver version: Mesa Gallium driver 21.3.3 for AMD Radeon RX 550 / 550 Series (POLARIS12, DRM 3.42.0, 5.15.12-200.fc35.x86_64, LLVM 13.0.0)
vainfo: Supported profile and entrypoints
      VAProfileMPEG2Simple            :	VAEntrypointVLD
      VAProfileMPEG2Main              :	VAEntrypointVLD
      VAProfileVC1Simple              :	VAEntrypointVLD
      VAProfileVC1Main                :	VAEntrypointVLD
      VAProfileVC1Advanced            :	VAEntrypointVLD
      VAProfileH264ConstrainedBaseline:	VAEntrypointVLD
      VAProfileH264ConstrainedBaseline:	VAEntrypointEncSlice
      VAProfileH264Main               :	VAEntrypointVLD
      VAProfileH264Main               :	VAEntrypointEncSlice
      VAProfileH264High               :	VAEntrypointVLD
      VAProfileH264High               :	VAEntrypointEncSlice
      VAProfileHEVCMain               :	VAEntrypointVLD
      VAProfileHEVCMain               :	VAEntrypointEncSlice
      VAProfileHEVCMain10             :	VAEntrypointVLD
      VAProfileJPEGBaseline           :	VAEntrypointVLD
      VAProfileNone                   :	VAEntrypointVideoProc

```

# Usage

 - Log into your google account (this does not integrate with your main browser)
 - To toggle full-screen mode, use the `Super + F` keyboard shortcut.

# Building from source

## Requirements

You will need to install [npm](https://www.npmjs.com/). On most distributions, the package is simply called `npm`.

This should work on any node version, but is currently tested & supported on v16 LTS.

## Building

```
npm install
npm start
```

On subsequent runs, `npm start` will be all that's required.

## Updating

Simply pull the latest version of master and install any changed dependencies:

```
git checkout master
git pull
npm install
npm start
```

# TODOs

 - Use OAuth for google sign-in
 - Check for vaapi compat on launch
 - Write vaapi installation instructions for some commonly used distros
 - Github action to version bump & release on master push 
