# Systems Hardening with Patch Manager via AWS Systems Manager
---
## **Objective**
Learn how to patch and verify compliance of Linux and Windows EC2 instances using AWS Systems Manager Patch Manager.
---
## **Steps Taken**

* Accessed AWS Console and opened AWS Systems Manager
* Patched Linux instances using the default AWS-AmazonLinux2DefaultPatchBaseline
* Created a **custom patch baseline** (`WindowsServerSecurityUpdates`) for Windows security updates
* Tagged Windows instances with `Patch Group: WindowsProd`
* Patched Windows instances using the custom baseline
* Verified compliance for all EC2 instances (Linux & Windows) in the Patch Manager dashboard
---
## **Challenges**

* Initially overlooked tagging for Windows instances, which prevented them from being selected in patching
* Resolved by adding the correct `Patch Group` tags before re-running the patch operation

---
## **Screenshot**
<img width="1920" height="923" alt="Screenshot (786)" src="https://github.com/user-attachments/assets/fbf0666a-dba9-43fc-8f3c-62a0018d258f" />
<img width="1920" height="876" alt="Screenshot (787)" src="https://github.com/user-attachments/assets/d3186b61-78f2-4f42-8255-be328511becf" />
<img width="1920" height="880" alt="Screenshot (788)" src="https://github.com/user-attachments/assets/b9dfacf4-ae67-40a1-9d0e-bd4afefcd15b" />
<img width="1920" height="876" alt="476299151-ae10eb99-c564-4900-a8f7-c6d611134df3" src="https://github.com/user-attachments/assets/84472692-d343-4cf7-9919-1ca02266cf96" />
<img width="1913" height="880" alt="Screenshot (790)" src="https://github.com/user-attachments/assets/d9bb9a42-ac8c-4da0-9602-44ea6a4c0eb7" />
<img width="1920" height="873" alt="Screenshot (791)" src="https://github.com/user-attachments/assets/2b3443ab-1176-4543-851a-d731a4a554cd" />
<img width="1911" height="867" alt="Screenshot (792)" src="https://github.com/user-attachments/assets/a6de4ee2-e763-4d0d-8768-2c6ef44429de" />

---
## **Takeaways**

* Patch Manager automates OS patching across Linux and Windows EC2 instances
* Custom patch baselines provide fine-grained control over update rules
* Correct instance tagging is critical for grouping and targeting in patch operations
* Compliance dashboards offer clear visibility into patch status across environments
