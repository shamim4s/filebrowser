<p align="center">
  <img src="[https://raw.githubusercontent.com/filebrowser/logo/master/banner.png](https://raw.githubusercontent.com/shamim4s/filebrowser/refs/heads/master/frontend/public/img/logo.svg)" width="550"/>
</p>

![Preview](https://user-images.githubusercontent.com/5447088/50716739-ebd26700-107a-11e9-9817-14230c53efd2.gif)



filebrowser provides a file managing interface within a specified directory and it can be used to upload, delete, preview, rename and edit your files. It allows the creation of multiple users and each user can have its own directory. It can be used as a standalone app.

> [!WARNING]
>
> This project is currently on **maintenance-only** mode, and is looking for new maintainers. For more information, please read the [discussion #4906](https://github.com/shamim4s/filebrowser/discussions/4906). Therefore, please note the following:
>
> - It can take a while until someone gets back to you. Please be patient.
> - [Issues][issues] are only being used to track bugs. Any unrelated issues will be converted into a [discussion][discussions].
> - No new features will be implemented until further notice. The priority is on triaging issues and merge bug fixes.
> 
> If you're interested in maintaining this project, please reach out via the discussion above.

[issues]: https://github.com/shamim4s/filebrowser/issues
[discussions]: https://github.com/shamim4s/filebrowser/discussions

## Features

File Browser is a **create-your-own-cloud-kind** of software where you can install it on a server, direct it to a path and then access your files through a nice web interface. You have many available features!

|    Easy Login System     |     Sleek Interface      |     User Management      |
| :----------------------: | :----------------------: | :----------------------: |
| ![](./docs/assets/1.jpg) | ![](./docs/assets/2.jpg) | ![](./docs/assets/3.jpg) |


|       File Editing       |     Custom Commands      |      Customization       |
| :----------------------: | :----------------------: | :----------------------: |
| ![](./docs/assets/4.jpg) | ![](./docs/assets/5.jpg) | ![](./docs/assets/6.jpg) |


## Install

For information on how to install File Browser, please check [docs/installation.md](./docs/installation.md).

## Configuration

For information on how to configure File Browser, please check [docs/configuration.md](./docs/configuration.md).

# My Install & configuration step

Download and Extract to C:\filebrowser

Run CMD with Administrator 
```
cd "C:\filebrowser"

rm filebrowser.db

.\filebrowser config init

.\filebrowser.exe users add admin password123 --perm.admin

.\filebrowser config set -r "C:\Users\Admin\Downloads" -p "8080" --address "192.168.10.70"  --database "C:\Program Files\filebrowser\filebrowser.db" --log "C:\Program Files\filebrowser\filebrowser.log" --branding.name "My Name" | .\filebrowser.exe

```

## Contributing

For information on how to contribute to the project, including how translations are managed, please check [docs/contributing.md](./docs/contributing.md).
