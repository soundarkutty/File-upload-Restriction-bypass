>  Step To Reproduce:
>
>  	The following steps outline the exploitation of the file upload Restriction bypass vulnerability in My Food Recipe 1.0 application.
>  
>  	    1.	Launch the My Food Recipe  V1.0 application
 
>  ![1](https://github.com/soundarkutty/File-upload-Restriction-bypass/assets/26168410/6c3f2676-01ff-4657-a9fa-58034ad260af)
> 
>  	    2.	Open Home and click the Edit image button instead of image  upload a php script fill the necessary column.
> 
>  ![image](https://github.com/soundarkutty/File-upload-Restriction-bypass/assets/26168410/5f9c2f48-305c-4067-b2e2-7cc685910906)

>  	   
> 
> ![image(1)](https://github.com/soundarkutty/File-upload-Restriction-bypass/assets/26168410/0a468b72-3008-4914-9438-4c4ca2b57c02)
>
>    3.	Click the Save changes button
>       
>       
>    4.	Right Click the Upload php file  in new tab and excute http://localhost/my-food-recipe/uploads/shell.php?cmd=whoami
>       
>![last](https://github.com/soundarkutty/File-upload-Restriction-bypass/assets/26168410/0430e5a6-f64a-4ab0-9f6b-988c1c9c2fc1)

>    5. Finally able to excute RCE command on the sytems      
> ------------------------------------------
>
> [Vulnerability Type]
>   file upload Restriction bypas
>
> ------------------------------------------
>
> [Vendor of Product]
>   https://www.sourcecodester.com
>
> ------------------------------------------
>
> [Affected Product Code Base]
>  My Food Recipe  V1.0  
>
> ------------------------------------------
>
> [Attack Type]
>   Remote
>
> ------------------------------------------
>
> [Impact Code execution]
>   true
>
> ------------------------------------------
>
> [Reference]
>  https://www.sourcecodester.com/php/16816/my-food-recipe-using-php-source-code.html
> 
> ------------------------------------------
>
> [Discoverer]
>   Soundar M