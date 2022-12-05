# dev.goats.testing.xivlauncher
Flatpak build files

It's pretty simple. First install flatpak builder. You can even install it via flatpak (from flathub):
`flatpak install flathub org.flatpak.Builder`

Once that's done, clone this git repo.

```
git clone https://github.com/rankynbass/dev.goats.testing.xivlauncher.git
```
Then make a directory to build into, and then build it.

```
mkdir -p flatpaks/xivlauncher
cd dev.goats.testing.xivlauncher
flatpak-builder --force-clean ../flatpaks/xivlauncher dev.goats.testing.xivlauncher.yml
```

Assuming there were no errors, you can install it with

```
flatpak-builder --user --install --force-clean ../flatpaks/xivlauncher dev.goats.testing.xivlauncher.yml
```

You can run it with `flatpak run dev.goats.testing.xivlauncher`, and it will also have a .desktop file that is exported as "XIVLauncher Testing".
