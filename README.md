# dev.goats.testing.xivlauncher
Flatpak build files

It's pretty simple. First install `flatpak-builder`. You can probably install it with your disto's package manager. If you can't do that, or you'd prefer to use flatpak, you can also install it from flathub:

```
flatpak install flathub org.flatpak.Builder//22.08
```

Then install the build dependencies (must be done in flatpak):

```
flatpak install flathub org.freedesktop.Sdk//22.08 org.freedesktop.Sdk.Extension.dotnet6//22.08
```

Once that's done, clone this git repo. 

```
git clone https://github.com/rankynbass/dev.goats.testing.xivlauncher.git
mkdir -p flatpaks/xivlauncher
cd dev.goats.testing.xivlauncher
```

> **If you installed `flatpak-builder` via flatpak, you need to replace `flatpak-builder` with `flatpak run org.flatpak.Builder` in the following commands**

Then finish the build with this command: 

```
flatpak-builder --force-clean ../flatpaks/xivlauncher dev.goats.testing.xivlauncher.yml
```

Assuming there were no errors, you can install it with

```
flatpak-builder --user --install --force-clean ../flatpaks/xivlauncher dev.goats.testing.xivlauncher.yml
```

After that, you can run it just like the normal flatpak: `flatpak run dev.goats.testing.xivlauncher`. There will also be a .desktop file, but if you have XIVLauncher already installed, it might have the exact same name (I've changed to XIVLauncher Testing for the master branch, but some of the others might not have that). For steam, you can set the launch options to `XL_SECRET_PROVIDER=FILE %command% run --parent-expose-pids --parent-share-pids --parent-pid=1 --branch=stable --arch=x86_64 --command=xivlauncher dev.goats.testing.xivlauncher`
