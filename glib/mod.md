 * Download [GLib 2.36.1](http://ftp.acc.umu.se/pub/gnome/sources/glib/2.36/glib-2.36.1.tar.xz)
 * Extract to `C:\mozilla-build\hexchat`
 * In `build\win32\vc11\glib.props`, replace:
	* `intl.lib` with `libintl.lib`
	* `<GlibEtcInstallRoot>..\..\..\..\vs10\$(Platform)</GlibEtcInstallRoot>` with  
`<GlibEtcInstallRoot>..\..\..\..\..\..\gtk\$(Platform)</GlibEtcInstallRoot>`
	* `<CopyDir>$(GlibEtcInstallRoot)</CopyDir>` with  
`<CopyDir>..\..\..\..\glib-2.36.1-rel</CopyDir>`
	* `<GlibSeparateVS11DllSuffix>-2-vs11</GlibSeparateVS11DllSuffix>` with  
`<GlibSeparateVS11DllSuffix>-2.0</GlibSeparateVS11DllSuffix>`
	* `<ClCompile>` with  
`<ClCompile><MultiProcessorCompilation>true</MultiProcessorCompilation>`
 * In `build\win32\vc11\glib.props`, add to `GlibDoInstall`
`copy $(SolutionDir)$(Configuration)\$(Platform)\bin\*.pdb $(CopyDir)\bin`
 * Open `build\win32\vc11\glib.sln` with VS
 * Build in VS
 * Release with `release-x86.bat`
 * Extract package to `C:\mozilla-build\hexchat\build\Win32`