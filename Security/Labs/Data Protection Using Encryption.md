# **Data Protection Using Encryption**

### **Objective**

Learn how to create an AWS KMS encryption key, encrypt plaintext data into ciphertext, and decrypt ciphertext back to plaintext using the AWS Encryption CLI.

---

### **Steps Taken**

1. **Access AWS Console**

   * Started the lab and logged in to AWS Management Console.
   * Opened **Key Management Service (KMS)** and created a **Symmetric key** with:

     ```
     Alias: MyKMSKey
     Description: Key used to encrypt and decrypt data files.
     ```
   * Copied the KMS Key ARN for later use.

2. **Connect to the EC2 File Server instance**

   * Opened **EC2** in the AWS Console → Selected **File Server** → Chose **Session Manager → Connect**.

3. **Configure AWS CLI credentials**

   ```bash
   cd ~
   aws configure
   # Temporary placeholders
   AWS Access Key ID: 1
   AWS Secret Access Key: 1
   Default region name: <your-region>
   Default output format: (Press Enter)

   vi ~/.aws/credentials
   # Replace with credentials from Vocareum AWS Details
   ```

4. **Install AWS Encryption CLI**

   ```bash
   pip3 install aws-encryption-sdk-cli
   export PATH=$PATH:/home/ssm-user/.local/bin
   ```

5. **Create plaintext files**

   ```bash
   touch secret1.txt secret2.txt secret3.txt
   echo 'TOP SECRET 1!!!' > secret1.txt
   cat secret1.txt
   ```

6. **Set KMS key ARN variable**

   ```bash
   keyArn=<your-KMS-ARN>
   ```

7. **Encrypt a file**

   ```bash
   mkdir output

   aws-encryption-cli --encrypt \
       --input secret1.txt \
       --wrapping-keys key=$keyArn \
       --metadata-output ~/metadata \
       --encryption-context purpose=test \
       --commitment-policy require-encrypt-require-decrypt \
       --output ~/output/.

   echo $?   # Check success (0 = success)
   ls output
   cat output/secret1.txt.encrypted
   ```

8. **Decrypt a file**

   ```bash
   cd output

   aws-encryption-cli --decrypt \
       --input secret1.txt.encrypted \
       --wrapping-keys key=$keyArn \
       --commitment-policy require-encrypt-require-decrypt \
       --encryption-context purpose=test \
       --metadata-output ~/metadata \
       --max-encrypted-data-keys 1 \
       --buffer \
       --output .

   ls
   cat secret1.txt.encrypted.decrypted
   ```

---

### **Challenges**

* **Issue:** Forgot to replace placeholder KMS ARN with the actual ARN → encryption failed.
  **Solution:** Updated `$keyArn` with the correct KMS ARN from AWS.

---


### **Takeaways**

* AWS KMS provides centralized key management for encrypting and decrypting data.
* The **AWS Encryption CLI** makes it easy to handle files securely from the command line.
* Always verify that:

  * Your **KMS key ARN** is correct.
  * Required IAM permissions are in place.
  * The encryption context matches between encryption and decryption commands.
