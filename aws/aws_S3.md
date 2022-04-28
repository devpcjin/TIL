# AWS S3에 파일 업로드하기

## 패키지 설치
`pip instal boto3`

- [bot3 documetation link](https://boto3.amazonaws.com/v1/documentation/api/latest/index.html)

## 코드 (ajax)
### Javascript
``` js
function save() {
            var form_data = new FormData($('#upload-file')[0]);
            $.ajax({
                type: 'POST',
                url: '/fileupload',
                data: form_data,
                processData: false,
                contentType: false,
                success: function (data) {
                    alert("파일이 업로드 되었습니다!!");
                },
            });
        }
```
### Python
``` py
@app.route('/fileupload', methods=['POST'])
def file_upload():
    file = request.files['file']
    s3 = boto3.client('s3')
    s3.put_object(
        ACL="public-read",
        Bucket="bucketpcj",
        Body=file,
        Key=file.filename,
        ContentType=file.content_type)
    return jsonify({'result': 'success'})
```
- `request.file['file']` : js로부터 전달 받은 파일
- `boto3.client('s3')` : S3를 나타내는 클라이언트
- `s3.put_object()` : 객체 설정
    - ``` py
        response = client.put_object(
        ACL='private'|'public-read'|'public-read-write'|'authenticated-read'|'aws-exec-read'|'bucket-owner-read'|'bucket-owner-full-control',
        Body=b'bytes'|file,
        Bucket='string',
        CacheControl='string',
        ContentDisposition='string',
        ContentEncoding='string',
        ContentLanguage='string',
        ContentLength=123,
        ContentMD5='string',
        ContentType='string',
        ChecksumAlgorithm='CRC32'|'CRC32C'|'SHA1'|'SHA256',
        ChecksumCRC32='string',
        ChecksumCRC32C='string',
        ChecksumSHA1='string',
        ChecksumSHA256='string',
        Expires=datetime(2015, 1, 1),
        GrantFullControl='string',
        GrantRead='string',
        GrantReadACP='string',
        GrantWriteACP='string',
        Key='string',
        Metadata={
            'string': 'string'
        },
        ServerSideEncryption='AES256'|'aws:kms',
        StorageClass='STANDARD'|'REDUCED_REDUNDANCY'|'STANDARD_IA'|'ONEZONE_IA'|'INTELLIGENT_TIERING'|'GLACIER'|'DEEP_ARCHIVE'|'OUTPOSTS'|'GLACIER_IR',
        WebsiteRedirectLocation='string',
        SSECustomerAlgorithm='string',
        SSECustomerKey='string',
        SSEKMSKeyId='string',
        SSEKMSEncryptionContext='string',
        BucketKeyEnabled=True|False,
        RequestPayer='requester',
        Tagging='string',
        ObjectLockMode='GOVERNANCE'|'COMPLIANCE',
        ObjectLockRetainUntilDate=datetime(2015, 1, 1),
        ObjectLockLegalHoldStatus='ON'|'OFF',
        ExpectedBucketOwner='string'
    )
      ```