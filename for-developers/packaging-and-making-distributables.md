# Packaging and Making Distributables

Packaging and making distributables is a simple process. However, please note that to make a package for an OS, you need to be on that OS \(excluding Windows zip—if you have Wine and Mono installed, you can build it on Linux or Mac as well\).

To make the distributables, just run `npm run make`. If you're on Linux, you should see something like this:

```text
✔ Checking your system
✔ Resolving Forge Config
We need to package your application before we can make it
✔ Preparing to Package Application for arch: x64
✔ Preparing native dependencies
✔ Packaging Application
Making for the following targets: zip, deb, rpm
✔ Making for target: zip - On platform: linux - For arch: x64
✔ Making for target: deb - On platform: linux - For arch: x64
✔ Making for target: rpm - On platform: linux - For arch: x64
```

This indicates that everything ran smoothly.

Then, to make the PKGBUILD for `pacman` distros, download the previous release's PKGBUILD. Change the version number under the `pkgver` variable. Finally, regenerate the checksum with `makepkg -g >> PKGBUILD`, and move the appended `md5sums=('<checksum here>')` where the previous line was \(replace it with this one\). It should be good to go.

### Making the .zip for Windows on other OSes \(requires Mono and Wine\)

With npx:

```bash
npx @electron-forge/cli make --platforms=win32 --targets=@electron-forge/maker-zip
```

Without:

```bash
node_modules/.bin/electron-forge make --platforms=win32 --targets=@electron-forge/maker-zip
```

### Issue with `maker-deb`

I've noticed that `maker-deb` doesn't work, because it complains about the Depends field in the control file. It will include something like this:

```text
'Depends' field, missing package name, or garbage where package name expected
```

For some reason, one of the values in the Depends field is `null` or `undefined`, which breaks `dpkg-deb`. To fix this, add the following line to `node_modules/electron-installer-common/src/template.js` after `await fs.ensureDir(path.dirname(dest), '0755')`:

```javascript
if (options.depends) options.depends.forEach((element, index) => { if (!element) options.depends.splice(index, 1) })
```

This just removes any null/undefined values from the `options.depends` array.

### MacOS fails to make the .dmg

Currently we don't offer a .dmg; the configuration is only there if it works in the future. The error can be safely ignored as the .zip was made successfully.

### Authoring a PKGBUILD \(for Arch Linux\)

The only change you'll need to make to the PKGBUILD is updating the MD5 hash of the source, which can be done with `makepkg -g >> PKGBUILD`. Then take the added line and use it to replace the existing one.

