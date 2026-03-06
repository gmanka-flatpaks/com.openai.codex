# codex flatpak

### install

```shell
sudo flatpak remote-add gmanka oci+https://gmanka-flatpaks.github.io
flatpak install gmanka com.openai.codex
```

### run

```shell
flatpak run com.openai.codex
```

### allow spawn commands on host

by default access to host system is restricted, but you can enable it:

```shell
sudo flatpak override com.openai.codex --talk-name=org.freedesktop.Flatpak
```

after that, codex will be able to access your host terminal via host-spawn tool, which is already inctluded in this flatpak package

### access to current working directory

```shell
flatpak run --filesystem=$PWD com.openai.codex
```

### access to host's /tmp

by default host's `/tmp` is not shared to the container

codex is usually writes something to host's `/tmp` dir and expects it to appear in flatpak sandbox

if you want shared `/tmp`, run this

```shell
sudo flatpak override com.openai.codex --filesystem=/var/tmp
sudo flatpak override com.openai.codex --filesystem=/tmp
```

### building codex flatpak from source

```shell
flatpak run org.flatpak.Builder --user --install --install-deps-from=flathub --force-clean --repo=repo build com.openai.codex.yml
```
