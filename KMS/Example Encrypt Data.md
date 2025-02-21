```bash
echo "find all the doggos, distract them with the yumz" > battleplans.txt

aws kms encrypt \
    --key-id alias/catrobot \
    --plaintext fileb://battleplans.txt \
    --output text \
    --query CiphertextBlob \
    | base64 --decode > not_battleplans.enc 
    
aws kms decrypt \
    --ciphertext-blob fileb://not_battleplans.enc \
    --output text \
    --query Plaintext | base64 --decode > decryptedplans.txt
```
- key-id - key id or alias to key id
- plaintext - data to encrypt
- output text - output of encrypt to text
- query CiphertextBlob - select the return field that contains the ciphertext
- | base64 --decode > not_battleplan.enc
	- take the returned encrypted plaintext, encode it as binary file