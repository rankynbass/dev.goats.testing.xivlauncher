# dev.goats.testing.xivlauncher
Flatpak build files

It's pretty simple. First install flatpak builder. You can even install it via flatpak (from flathub):
`flatpak install flathub org.flatpak.Builder`

Once that's done, clone this git repo. 

```
git clone https://github.com/rankynbass/dev.goats.testing.xivlauncher.git
mkdir -p flatpaks/xivlauncher
cd dev.goats.testing.xivlauncher
```
If you want to test the dxvk backend patches without the UI updates (basically, just test that the XIVLauncher.Common.Unix changes don't break anything), you can change to the appropriat branch with  `git checkout 1.0.2+new-dxvk-settings`.

Then finish the build with

```
flatpak-builder --force-clean ../flatpaks/xivlauncher dev.goats.testing.xivlauncher.yml
```

Assuming there were no errors, you can install it with

```
flatpak-builder --user --install --force-clean ../flatpaks/xivlauncher dev.goats.testing.xivlauncher.yml
```

You can run it with `flatpak run dev.goats.testing.xivlauncher`, and it will also have a .desktop file that is exported as "XIVLauncher Testing". (The `1.02+new-dxvk-settings` branch will actually just make an "XIVLauncher" .desktop entry. I haven't changed the .desktop file in that branch). 
