There are three ways to create a data URL from file. Two way for any type of files and one specific way for images.

1.Method =>Using URL createObject
2.Method =>Using newFileReader()
3.Method => Using Canvas API (Special way to create a data URL form a image)


Method 1 =>
==Using URL CreateObjectURL==

```js
flPictureElm.addEventListener('change', (e) => {  
    alert("File Selected");  
    if (flPictureElm.files.length) {  
  
         const imageFile = flPictureElm.files.item(0);        
        const imageBlob= new Blob([imageFile], { type: imageFile.type });     const dataURL = URL.createObjectURL(imageFile);            pictureElm.style.background = `url('${dataURL}')`;  
    

    } else {  
        alert("No File Selected");  
    }  
});
```

Method 2 => 
==Using `newFileReader()`==

```js
const fr = newFileReader( );
fr.addEVentListner('load',(e) =>{
(e.target.result);
});

fr.readxxx(file/blob);
//can be used as a dataURL, string ..... so on
```

link to the file api =>https://developer.mozilla.org/en-US/docs/Web/API/File


Above two methods can be use for any type of file

Method 3 => 
==Using canvas api==

This is only for image. Only way to send the web cam images to the back end

This  method can be used to URL convert to a data URL / image element to a file.
This method also can be used to add water marks

![[Pasted image 20240619175621.png]]
`toDataURL` can be used to convert the canvas to a data url. Data URL also can be used to store the file in backend. 

this is the gitHub link => https://github.com/IJSE-Direct-Entry-Program-12/web-api/blob/main/8-ajax/js/example-3.js


