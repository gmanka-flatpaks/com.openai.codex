# codex flatpak

### building

```shell
flatpak run org.flatpak.Builder --user --install --install-deps-from=flathub --force-clean --repo=repo build com.openai.codex.yml
```

### access to host system

by default access to host system is restricted, but you can enable it:

```shell
sudo flatpak override com.openai.codex --talk-name=org.freedesktop.Flatpak
```

after that, codex will be able to access your host terminal via host-spawn tool, which is already inctluded in this flatpak package

