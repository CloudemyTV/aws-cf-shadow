# AWS CloudFormation Template for Shadowsocks VPN

## Step 1:

- Upload the template to AWS CloudFormation
- CloudFormation will create the Shadowsocks server for you
- Take a note of the Password you have set for the server, you will need it for Shadowsocks Client to connect to the server

## Step 2:

- Download Shadowsocks client
- Windows Client: https://github.com/shadowsocks
- Android Client: https://github.com/shadowsocks/shadowsocks-android
- iOS: Sockswitch is recommended
- MacOS & Linux: https://sourceforge.net/projects/shadowsocksgui/files/dist/ 


## Troubleshooting

- In case the IP of Shadowsocks has been blocked, you can easily *Stop Then Start* (Do Not Just Reboot, Reboot won't assign new IP) the server using AWS CLI
- Replace i-XXXXXXXX with the actual EC2 Instance ID

*Stop EC2*
```
aws ec2 stop-instances --instance-ids i-XXXXXXXX
```

*Start EC2*
```
aws ec2 start-instances --instance-ids i-XXXXXXXX
```

*Describe IP Address*
```
aws ec2 describe-instances --instance-ids i-XXXXXXXX --query 'Reservations[*].Instances[*].PublicIpAddress' --output text
```



Note: please this is for Educational Purpose only. Do not use it in countries or regions that forbid VPN access.
