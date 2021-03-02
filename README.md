## Requirements

| Name | Version |
|------|---------|
| terraform | >= 0.12.0 |

## Providers

| Name | Version |
|------|---------|
| aws | n/a |

## Modules

No Modules.

## Resources

| Name |
|------|
| [aws_ebs_volume](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/ebs_volume) |
| [aws_instance](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/instance) |
| [aws_route53_record](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/route53_record) |
| [aws_volume_attachment](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/volume_attachment) |

## Inputs

| Name | Description | Type | Default | Required |
|------|-------------|------|---------|:--------:|
| ami | The AMI to use for the instance. | `string` | n/a | yes |
| application | Application (e.g. `cd` or `clouddrove`). | `string` | `""` | no |
| assign\_eip\_address | Assign an Elastic IP address to the instance. | `bool` | `false` | no |
| associate\_public\_ip\_address | Associate a public IP address with the instance. | `bool` | `true` | no |
| attributes | Additional attributes (e.g. `1`). | `list` | `[]` | no |
| availability\_zone | Availability Zone the instance is launched in. If not set, will be launched in the first AZ of the region. | `list` | `[]` | no |
| cpu\_core\_count | Sets the number of CPU cores for an instance. | `string` | `null` | no |
| cpu\_credits | The credit option for CPU usage. Can be `standard` or `unlimited`. T3 instances are launched as unlimited by default. T2 instances are launched as standard by default. | `string` | `"standard"` | no |
| delimiter | Delimiter to be used between `organization`, `environment`, `name` and `attributes`. | `string` | `"-"` | no |
| disable\_api\_termination | If true, enables EC2 Instance Termination Protection. | `bool` | `false` | no |
| disk\_size | Size of the root volume in gigabytes. | `number` | `8` | no |
| dns\_enabled | Flag to control the dns\_enable. | `bool` | `false` | no |
| dns\_zone\_id | The Zone ID of Route53. | `string` | `""` | no |
| ebs\_block\_device | Additional EBS block devices to attach to the instance. | `list` | `[]` | no |
| ebs\_device\_name | Name of the EBS device to mount. | `list(string)` | <pre>[<br>  "/dev/xvdb",<br>  "/dev/xvdc",<br>  "/dev/xvdd",<br>  "/dev/xvde",<br>  "/dev/xvdf",<br>  "/dev/xvdg",<br>  "/dev/xvdh",<br>  "/dev/xvdi",<br>  "/dev/xvdj",<br>  "/dev/xvdk",<br>  "/dev/xvdl",<br>  "/dev/xvdm",<br>  "/dev/xvdn",<br>  "/dev/xvdo",<br>  "/dev/xvdp",<br>  "/dev/xvdq",<br>  "/dev/xvdr",<br>  "/dev/xvds",<br>  "/dev/xvdt",<br>  "/dev/xvdu",<br>  "/dev/xvdv",<br>  "/dev/xvdw",<br>  "/dev/xvdx",<br>  "/dev/xvdy",<br>  "/dev/xvdz"<br>]</pre> | no |
| ebs\_iops | Amount of provisioned IOPS. This must be set with a volume\_type of io1. | `number` | `0` | no |
| ebs\_optimized | If true, the launched EC2 instance will be EBS-optimized. | `bool` | `false` | no |
| ebs\_volume\_enabled | Flag to control the ebs creation. | `bool` | `false` | no |
| ebs\_volume\_size | Size of the EBS volume in gigabytes. | `number` | `30` | no |
| ebs\_volume\_type | The type of EBS volume. Can be standard, gp2 or io1. | `string` | `"gp2"` | no |
| encrypted | If true, the disk will be encrypted. | `bool` | `false` | no |
| environment | Environment (e.g. `prod`, `dev`, `staging`). | `string` | `""` | no |
| ephemeral\_block\_device | Customize Ephemeral (also known as Instance Store) volumes on the instance. | `list` | `[]` | no |
| host\_id | The Id of a dedicated host that the instance will be assigned to. Use when an instance is to be launched on a specific dedicated host. | `string` | `null` | no |
| hostname | DNS records to create. | `string` | `""` | no |
| iam\_instance\_profile | The IAM Instance Profile to launch the instance with. Specified as the name of the Instance Profile. | `string` | `""` | no |
| instance\_count | Number of instances to launch. | `number` | `1` | no |
| instance\_enabled | Flag to control the instance creation. | `bool` | `true` | no |
| instance\_initiated\_shutdown\_behavior | Shutdown behavior for the instance. | `string` | `""` | no |
| instance\_profile\_enabled | Flag to control the instance profile creation. | `bool` | `false` | no |
| instance\_tags | Instance tags. | `map` | `{}` | no |
| instance\_type | The type of instance to start. Updates to this field will trigger a stop/start of the EC2 instance. | `string` | n/a | yes |
| ipv6\_address\_count | Number of IPv6 addresses to associate with the primary network interface. Amazon EC2 chooses the IPv6 addresses from the range of your subnet. | `number` | `0` | no |
| ipv6\_addresses | List of IPv6 addresses from the range of the subnet to associate with the primary network interface. | `list` | `[]` | no |
| key\_name | The key name to use for the instance. | `string` | `""` | no |
| kms\_key\_id | The ARN for the KMS encryption key. When specifying kms\_key\_id, encrypted needs to be set to true. | `string` | `""` | no |
| label\_order | Label order, e.g. `name`,`application`. | `list` | `[]` | no |
| managedby | ManagedBy, eg 'CloudDrove' or 'AnmolNagpal'. | `string` | `"anmol@clouddrove.com"` | no |
| monitoring | If true, the launched EC2 instance will have detailed monitoring enabled. (Available since v0.6.0). | `bool` | `false` | no |
| name | Name  (e.g. `app` or `cluster`). | `string` | `""` | no |
| network\_interface | Customize network interfaces to be attached at instance boot time. | `list(map(string))` | `[]` | no |
| placement\_group | The Placement Group to start the instance in. | `string` | `""` | no |
| root\_block\_device | Customize details about the root block device of the instance. See Block Devices below for details. | `list` | `[]` | no |
| source\_dest\_check | Controls if traffic is routed to the instance when the destination address does not match the instance. Used for NAT or VPNs. | `bool` | `true` | no |
| subnet | VPC Subnet ID the instance is launched in. | `string` | `null` | no |
| subnet\_ids | A list of VPC Subnet IDs to launch in. | `list(string)` | `[]` | no |
| tags | Additional tags (e.g. map(`BusinessUnit`,`XYZ`). | `map` | `{}` | no |
| tenancy | The tenancy of the instance (if the instance is running in a VPC). An instance with a tenancy of dedicated runs on single-tenant hardware. The host tenancy is not supported for the import-instance command. | `string` | `""` | no |
| ttl | The TTL of the record to add to the DNS zone to complete certificate validation. | `string` | `"300"` | no |
| type | Type of DNS records to create. | `string` | `"CNAME"` | no |
| user\_data | The Base64-encoded user data to provide when launching the instances. | `string` | `""` | no |
| vpc\_security\_group\_ids\_list | A list of security group IDs to associate with. | `list(string)` | `[]` | no |

## Outputs

No output.
