 * Download [GDK-PixBuf 2.28.1](http://ftp.gnome.org/pub/gnome/sources/gdk-pixbuf/2.28/gdk-pixbuf-2.28.1.tar.xz)
 * Extract to `C:\mozilla-build\hexchat`
 * In `build\win32\vc12\gdk-pixbuf.props`, replace:
	* `intl.lib` with `libintl.lib`
	* `<GlibEtcInstallRoot>..\..\..\..\vs$(VSVer)\$(Platform)</GlibEtcInstallRoot>` with
`<GlibEtcInstallRoot>..\..\..\..\..\..\gtk\$(Platform)</GlibEtcInstallRoot>`
	* `<GlibEtcInstallRootFromBuildWin32>..\..\..\vs$(VSVer)\$(Platform)</GlibEtcInstallRootFromBuildWin32>` with
`<GlibEtcInstallRootFromBuildWin32>..\..\..\..\..\gtk\$(Platform)</GlibEtcInstallRootFromBuildWin32>`
	* `<CopyDir>$(GlibEtcInstallRoot)</CopyDir>` with
`<CopyDir>..\..\..\..\gdk-pixbuf-2.28.1-rel</CopyDir>`
	* `<GdkPixbufSeparateVSDllSuffix>-2-vs$(VSVer)</GdkPixbufSeparateVSDllSuffix>` with
`<GdkPixbufSeparateVSDllSuffix>-2.0</GdkPixbufSeparateVSDllSuffix>`
 * In `build\win32\vc12\gdk-pixbuf.props`, add to `GdkPixbufDoInstall`:
`copy $(Configuration)\$(Platform)\bin\*.pdb $(CopyDir)\bin`
 * Replace `libpng15.lib` with `libpng16.lib` in `build\win32\vc12\gdk-pixbuf.vcxproj`
 * Open `build\win32\vc12\gdk-pixbuf.sln` with VS
 * Build in VS
 * Release with `release-x86.bat`
 * Extract package to `C:\mozilla-build\hexchat\build\Win32`
