# What is an XAPK file?

The acronym of XAPK stands for : eXtended Android Package Kit

An XAPK file is a new Android format for installing applications that is very similar to the standard .APK format.

Instead the .XAPK file contains other resources to make the app work which unfortunately is not a standard package, it must be installed with special installers available from the Market

An XAPK file would be a ZIP file that contains within it an APK file to install the application and more additional data such as OBB resources to run the application or game without downloading anything else, this is useful for applications or large games.

Very useful if you want to upload an app that requires other additional resources, some sites support the XAPK format (Uptodown, APKPure), instead of uploading APK + OBB you can create an XAPK file that contains both.

And XAPKs can be created by having the APK file and OBB files of the application, there is a program called XAPK Creator that makes them created by filling in fields (The only flaw, with XAPKs created with XAPK Creator are not installed correctly with installers, manual installation is recommended) (For best results create XAPK manually)

### I remember that on Play Store XAPK files are not supported!

# How to View a XAPK File

It is possible to view the internal contents of an XAPK file without extraction thanks to a small program called XAPK Viewer

The link can be found at the bottom of the page

# How to create an XAPK file

### Manually Creation
Manual Creation (Recommended)

First of all you need the APK file + OBB files of the application with the same version.

Then you will need a program called APK Editor Studio which will let you view all the information of the APK file such as images, manifests etc.

Once you have this information, create a folder.
and inside it create us a file called "manifest.json"
and you will have to write us all the information that identifies the application in question, such as its version, its permissions, the package name, the location of the OBB files, etc.

Here you can see the structure of a manifest.json

```json
{
"xapk_version":1,
"package_name":"${ApplicationId}",
"name":"${AppName}",
"version_code":"${versionCode}",
"version_name":"${versionName}",
"min_sdk_version":"${minSdkVersion}",
"target_sdk_version":"${targetSdkVersion}",
"permissions":[
    "android.permission.INTERNET"
],
"total_size":65535,
"expansions":[
  {
    "file":"Android/obb/${ApplicationId}/main.${versionCode}.${ApplicationId}.obb",
    "install_location":"EXTERNAL_STORAGE",
    "install_path":"Android/obb/${ApplicationId}/main.${versionCode}.${ApplicationId}.obb"
  }
]
}
```
Then after completing the manifest.json, rename the APK file to the application package name as "packagename.apk", after that you can also copy an application icon and rename it to "icon.png", then create a folder called "Android\obb\packagename\main.codeversion.packagename.obb". after that also copy the OBB files to the correct paths and going to the root of the folder you can compress all the files as ZIP and after compressing the ZIP file rename the extension to .XAPK and your .XAPK file is ready to be installed or stored

### Simplified creation

If you don't want to perform all the operations listed above, you can download XAPK Creator which is a small program that creates an XAPK file giving it all the application information, specifying APK + OBB files. The only flaw is that XAPK files created with this little program are not installed correctly by XAPK installers. manual installation is recommended

# How to Install an XAPK file

First you need to specify that the .XAPK files are similar to the APK format, but they are not recognized by the normal package installer included in Android, there are two ways to install them

### Installation with specific installers for XAPK

Here you have to go to the Play Store and search for the word "XAPK Installer", and various Apps that install XAPK files will appear, just install one, specify the XAPK file you want to install, then you will be asked during the installation to install the APK file contained within the XAPK file, simply do "Install", and after the end of the installation the app will work immediately without asking you to download additional data from the internet.

### Manual Installation

If it is a manual installation, you need to install an app from the Play Store called "ZArchiver".
after installation open the app and rename the XAPK changing its extension to ZIP, practical example "toca_kitchen_2_full.xapk" to "toca_kitchen_2_full.zip", after renaming it you have to extract the ZIP file, after the extraction you will see an APK file plus a folder called android. first install the APK file, then copy the folder with the application package name contained in "Android/obb/packagename" to "Android/obb/packagename".

# Download programs to manage XAPK files

[XAPK Creator](https://github.com/Sorecchione07435/XAPKCreator_English/) - For Create a file XAPK

[XAPK Viewer](https://github.com/Sorecchione07435/XAPKViewer) - For View a Existing XAPK

[APK Editor Studio](https://qwertycube.com/apk-editor-studio) - For View APK Specifics
