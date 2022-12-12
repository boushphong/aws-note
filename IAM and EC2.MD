### IAM
- A root account in AWS has all priviledges
- Best practices: The root account can then create an account that is suitable for administration (Admin account)
- All operations will be mostly handled by the admin account
- The admin account can then create user accounts: 
    - The user account could be attached with specific IAM Group permission (Eg: Read S3 Bucket Group) (For multiple employees within a department)
    - The user account could also have specific permissions assigned specificly just for the users

### EC2
- EC2 will be attached to a default VPC with a private IP.
- EC2's public IP will be addressed randomly everytime you restart the instance. (For static IP's, use Elastic IP Service)
- You can define Security Group within an EC2 instance. Security Group let a specific public IP's to access the EC2 instance. Even instances created within your AWS account, you still need define Security Group so they could talk to each others. 
- Amazon AMI let you create you custom EC2 VMs with pre-defined configs for faster bootups for later uses.  

### EC2 Block Storage
- An EBS (Elastic Block Store) Volume is a network drive you can attach to your instance while they run.
- It allows your instances to persist data, even after the instance's termination.
- Can only be mounted to one instance at a time (An EBS volume is bounded to a specific avalability zone) (To move across AZ, you must snapshot the volume)
- Can be detached from an EC2 instance and attached to another one quickly (suited to do fail-over)
- Most EBS volumes can only be attached to only one EC2 instance at a time. An instances can have multiple EBS volumes being attached to it at once.
- Some EBS volumes can be multi-attached to several instances (io1/io2 family). The EBS will use a Cluster-Awared file system. Applications running on multiple instaces will have full read/write permissions to the same EBS volume.


### EC2 Instance Storage

<img width="1082" alt="image" src="https://user-images.githubusercontent.com/59940078/207056061-3de4da1a-608c-4403-accf-972647ab68ea.png">
