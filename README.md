# SACO2_DataSecurity

Data between the client and RDS can be encrypted via SSL/TLS.. and this encryption can be set to mandatory 

RDS supports EBS encryption(using KMS) for the data which is stored at rest in EBS Volume

EBS encryption is handled by RDS Host and underlying EBS based storage (means RDS just stores the data, but the host on which the RDS is running manages the encryption process)

We can use AWS manged CMS or Customer Managed CMK to generate data keys and these data keys are used for actual encrytion operation

When we use these type of encryption Storage,logs,replicas, EVERYHTING is encrypted using the same master key

Encryption can not be removed once it's added

TDE stands for transparent data encryption

RDS Oracle and RDS MSSQL support TDE. This encryption is handled by database engine itself(not by RDS host, the RDS is running on)

RDS oracle supports TDE using CloudHSM. CloudHSM is managed by you, not by AWS. So you can say the data is more secure because you have the major control

Logins to database are don eby local database users. They are not IAM users, they are outside of control of aws. One gets created when you provision an RDS instance. You can configure RDS to allow IAM user to authenticate to database.
(SEE the diagrams to understand architecture)
