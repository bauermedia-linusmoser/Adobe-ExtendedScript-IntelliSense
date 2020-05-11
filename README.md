# Types for Adobe - Visual Studio Code IntelliSense for Adobe CEP Panel Projects

This project is based on the [Types-for-Adobe](https://github.com/pravdomil/Types-for-Adobe) repository by [pravdomil](https://github.com/pravdomil). 

While the original repo is focussed on installing all typings (via npm) for the usage with TypeScript, this fork focusses on the usage with regular ExtendedScript (.jsx files) for the creation of Adobe CEP panels. This allows to enhance the Visual Studio Code IntelliSense and offer suggestions and other IntelliSense features in your ExtendedScript file(s).

## Usage with Visual Studio Code
The following manual assumes that you are following the Adobe recommendations for [structuring your Adobe CEP panel project](https://github.com/Adobe-CEP/Getting-Started-guides#1-decide-the-folder-structure). 

### 1. Download the whole repository
First of all, please download all files from this repository (don't worry, you won't need all of them later). 

### 2. Copy the declaration files
Inside the downloaded repository, switch to the folder with the Adobe application and version of your choice (e.g. `InDesign/2018`) and copy the `index.d.ts` file inside this folder into your Adobe CEP panel project. While you can just copy the file into the root directory of your extension folder, I recommend creating a new subfolder like `dev/types/`.

Depending on the declaration file you are using, you will also need some shared files. To play it safe, just copy the whole `shared` folder from the root directory of the downloaded repo into the newly created `dev/types/` folder in your CEP extension folder.

### 3. `tsconfig.json`
Great, you have now all declaration files in place. For IntelliSense to work properly with these file, you will need a `tsconfig.json`. Please feel free to use the provided file in the root directory of this repo and copy it into the root directory of your Adobe CEP extension folder.

### 4. `settings.json`
Just one more step: You must make Visual Studio Code aware, that it should handle your .jsx ExtendedScript files like regular JavaScript (otherwise, the IntelliSense autocomplete won't work). So simply place a `settings.json` into your `.vscode` folder (if you don't have one already, simply create it in the root of your CEP extension folder), which must contain the following:

```
{
    "files.associations": {
        "*.jsx": "javascript",
        "*.debug": "xml"
    }
}
```

You may also just copy the provided `settings.json` file in the root of this repo.

### 5. Enjoy IntelliSense support for ExtendedScript
Awesome, you are all done! Your project folder should now look roughly like this:

<img src="https://github.com/bauermedia-linusmoser/Adobe-ExtendedScript-IntelliSense/blob/master/_resources/vscode-explorer.png" width="25%">


Just switch to your ExtendedScript `.jsx` file and enjoy IntelliSense! :)

## Notice

I am **not** the original author of the declaration files, these were made by [pravdomil](https://github.com/pravdomil). Please feel free to support the original author by [buying him a beer](https://www.paypal.com/cgi-bin/webscr?cmd=_s-xclick&hosted_button_id=BCL2X3AFQBAP2&item_name=types-for-adobe%20Beer).

I stumbled upon these delaration files when I was looking for a way to enable ExtendedScript IntelliSense support for my Adobe CEP Panel project inside Visual Studio Code. As I was struggling to get IntelliSense working properly, I came up with this little project - intended to help others in the same situation.
