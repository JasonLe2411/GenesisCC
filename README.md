# GenesisCC
This is a small project to understand RSA algorithm and sharding private keys 

**Building the app**

*Modules & Libraries*
Crypto.Random\
Crypto.PublicKey.RSA\
Crypto.Cipher.PKCS1_OAEP\
random\
base64

*Process* 
- Generate key pair 
- Write public key to file 
- Put private key into linear equations for sharding (y=ax+b), where 'a' are the elements of the private key like d,q,p and u. 'x' and 'b' are randomized
Users are given 'y' and the rest are hidden 
- Write shards to file (shards will not be written as key format since they are not keys yet)
- Import 2 shards
- Solve linear equations of 2 shards to find 'a'

*Security* 
- Both 'x' and 'b' are randomized between 1 and 1000000, and all are hidden from the user along with the attributes of the private key. Therefore it would be very hard for someone with 1 shard to test out the private key.
- The key can be solved by combining 2 key shards together

*Testing*
- Cd into the program's directory 
- Type 'python systemfile' into cmd
- Follow the file's prompt 

Tech demo video: 
https://youtu.be/tqNbmlbKfHw
