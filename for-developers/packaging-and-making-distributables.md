# Packaging and Making Distributables

Packaging and making distributables is a simple process. However, please note that to make a package for an OS, you need to be on that OS. This does not apply to the `.zip` package.

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

### Issue with `maker-deb`

I've noticed that `maker-deb` doesn't work, because it complains about the Depends field in the control file. It will include something like this:

```text
'Depends' field, missing package name, or garbage where package name expected
```

For some reason, one of the values in the Depends field is `null`, which breaks `dpkg-deb`. To fix this, add the following line to `node_modules/electron-installer-common/src/template.js` after `await fs.ensureDir(path.dirname(dest), '0755')`:

```javascript
if (options.depends) options.depends.forEach((element, index) => { if (!element) options.depends.splice(index, 1) })
```

This just removes any null values from the `options.depends` array.

