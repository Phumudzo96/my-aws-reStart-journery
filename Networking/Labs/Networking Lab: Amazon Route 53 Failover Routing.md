# Networking Lab: Amazon Route 53 Failover Routing
## Objective
Configure Route 53 failover routing to maintain high availability for a web application.

## Steps Taken
✅ Verified café application running on two EC2 instances in different Availability Zones.  
✅ Configured a Route 53 Health Check with SNS email notifications.  
✅ Created primary (failover) A record for the café primary website.  
✅ Created secondary (standby) A record for the café secondary website.  
✅ Tested DNS resolution for the domain.  
✅ Simulated failover by stopping the primary EC2 instance.  
✅ Verified Route 53 failed over traffic to the secondary instance automatically.  
✅ Confirmed SNS email alerts triggered on health check failure.  

## Challenges
❌ DNS failover takes a few minutes due to TTL and health check propagation.  
❌ Waiting patiently and refreshing health checks ensured proper validation.  

## Screenshot
<img width="1920" height="946" alt="Screenshot (732)" src="https://github.com/user-attachments/assets/40742e4e-c5de-41c1-8c5d-fbd525bf39d1" />
<img width="1920" height="939" alt="Screenshot (733)" src="https://github.com/user-attachments/assets/71a52380-cb38-4a25-8be4-3d4c00996af9" />
<img width="1920" height="876" alt="Screenshot (734)" src="https://github.com/user-attachments/assets/f955f7c5-052e-4cc7-8824-2bba50e1b0be" />
<img width="1920" height="873" alt="Screenshot (735)" src="https://github.com/user-attachments/assets/0c08b3f2-afa8-4886-96f9-0866801e308f" />
<img width="1920" height="876" alt="Screenshot (736)" src="https://github.com/user-attachments/assets/e37798f5-dbc6-4335-872c-d3fc015e153c" />
<img width="1920" height="862" alt="Screenshot (737)" src="https://github.com/user-attachments/assets/5735d890-b394-48e6-b52c-d80e83f94ae1" />
<img width="1920" height="935" alt="Screenshot (738)" src="https://github.com/user-attachments/assets/6a56a833-f3f3-4cce-ae11-3ed2c4083925" />
<img width="1920" height="933" alt="Screenshot (739)" src="https://github.com/user-attachments/assets/3a6ece0b-372a-4a55-abf0-98ca298baee0" />


## Takeaways
✅ Route 53 can handle DNS-based failover automatically to increase availability.  
✅ Health checks can monitor endpoints and trigger alerts when resources become unhealthy.  
✅ Combining health checks, SNS notifications, and failover routing creates a robust disaster recovery approach for web workloads.  
✅ Testing failover regularly ensures readiness during real-world outages.  

## Architectural diagram
<img width="818" height="708" alt="Amazon Route 53 Failover Routing" src="https://github.com/user-attachments/assets/2c46f1b3-78ab-4c90-8531-7393ccd784a6" />

