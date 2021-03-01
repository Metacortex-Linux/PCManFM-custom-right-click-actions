# PCManFM-custom-right-click-actions

mkdir -p /usr/local/share/file-manager/actions

Current actions:
- Create new launcher
- File Hash
- Open as root
- Open Terminal Here
- Set As Wallpaper

**### Open Folder as root**

    [Desktop Entry]
    Type=Action
    Icon=dialog-password
    Name=Open as root
    Name[ru]=Открыть как Администратор
    Profiles=profile-0;profile-1;
    
    [X-Action-Profile profile-0]
    MimeTypes=inode/directory;
    TryExec=pcmanfm
    Exec=gksudo pcmanfm %f
    
    [X-Action-Profile profile-1]
    MimeTypes=text/*;
    TryExec=geany
    Exec=gksudo geany %f

**### Open Terminal Here**

    [Desktop Entry]
    Type=Action
    Tooltip=Open Terminal Here
    Name=Open Terminal
    Profiles=profile-one;
    Icon=lxterminal
    
    [X-Action-Profile profile-one]
    MimeTypes=inode/directory;
    Exec=lxterminal
    Name=Default profile

**### Create new launcher**

    [Desktop Entry]
    Type=Action
    Icon=gnome-panel-launcher
    Name=Create new launcher
    Name[ru]=Создать кнопку запуска
    Profiles=profile-zero;
    
    [X-Action-Profile profile-zero]
    Name=Default profile
    Name[ru]=Default profile
    MimeTypes = inode/directory;
    SelectionCount = < 2
    TryExec=new-desktop-item-edit
    Exec=sh -c "LD_LIBRARY_PATH=/usr/local/lib/x86_64-ext/ new-desktop-item-edit --create-new "./""

**### File Hash**

> sudo apt install gtkhash

    [Desktop Entry]
    Name=File Hash
    Name[ru]=Контрольная сумма
    Type=Action
    Profiles=on_file
    Icon=gtkhash
    
    [X-Action-Profile on_file]
    MimeTypes=all/allfiles;!inode/directory;
    TryExec=gtkhash
    Exec=gtkhash %f

**### Find Here**

> sudo apt install catfish

    [Desktop Entry]
    Type=Action
    Icon=system-search
    Name=Find here
    Name[ru]=Поиск в этом каталоге
    Profiles=profile-0;
    
    [X-Action-Profile profile-0]
    MimeTypes=inode/directory;
    TryExec=catfish
    Exec=catfish %f

**### Set As Wallpaper**

    [Desktop Entry]
    Type=Action
    Icon=gnome-fs-desktop
    ToolbarLabel=Set Wallpaper
    Name=Set Wallpaper
    Name[ru]=Установить на Рабочий стол
    Profiles=profile-zero;
    
    [X-Action-Profile profile-zero]
    MimeTypes=image/*;
    Exec=pcmanfm -w %f


