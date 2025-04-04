# limit-media-upload-size
snippet to prevent uploading huge images on your site
To customize the value, you can change the value of $fileSize according to your needs. In the snippet provided, the default maximum upload file size is set to 512 KB. When this value is multiplied by 1024 kilobytes, it converts to 512 KB * 1024 bytes/KB = 524,288 bytes, which is 0.5 megabytes (MB). Just remember that 1024 KB = 1 MB. So as an example, if you want to set the maximum upload file size to 2 MB, you would provide the file size as ‘2048’ KB.

After adding this snippet to your site, and try to upload an image that is larger than the size specified in the code.

```
// Function to limit the upload file size
function pac_da_limit_upload_file_size( $size ) {
    $fileSize = '512'; // Provide fileSize in KB's, 512 value means 512 KBs
    $size = (int)$fileSize * 1024; // Convert KB to bytes
    return $size;
}

// Hook the function to the 'upload_size_limit' filter with a priority of 20
add_filter( 'upload_size_limit', 'pac_da_limit_upload_file_size', 20 );
```
