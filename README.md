# AWS WorkSpace Setup Simulation for Remote Help Desk

## 📋 Project Overview

This project simulates the provisioning of a secure, cloud-based Windows desktop environment using **AWS WorkSpaces**. It is designed to reflect a typical use case for onboarding remote employees and supporting help desk ticket workflows.

**Role**: Junior Cloud/Help Desk Technician  
**IAM User**: `jamie`  
**Tools Used**: AWS Console (WorkSpaces, IAM), Screenshots, Documentation

## 📁 Project Structure

<p align="center">
  <img 
    src="https://github.com/user-attachments/assets/e777b23f-ca24-4bd2-add7-3a304a865876" 
    height="35%" 
    width="35%" 
    alt="AWS WorkSpace Setup Simulation for Remote Help Desk_IMAGE"
  />
</p>

---

## 🚀 Step-by-Step Setup

### Step 1: Create IAM User - `jamie`
- Navigate to **IAM** in the AWS Console.
- Create a new user named `jamie`.
- Assign the user to the group: `WorkSpacesUsers`.
- Attach the following **least-privilege** policies:
  - `AmazonWorkSpacesSelfServiceAccess`
  - `AmazonWorkSpacesWebReadOnly`

<p align="center">
  <img 
    src="https://github.com/user-attachments/assets/68230c0c-a028-447e-a6a1-1dc239503063" 
    height="45%" 
    width="45%" 
    alt="Create IAM User Jamie"
  />
</p>



---

### Step 2: Set Up Directory (Simple AD)
- Navigate to **Directory Service** in the AWS Console.
- Select **Set up directory > Simple AD**.
- Fill in the required fields (DNS, NetBIOS name, password).
- Wait for the directory provisioning to complete.


<p align="center">
  <img 
    src="https://github.com/user-attachments/assets/31dbd18f-f277-475a-890f-56aa7102a032"
    height="45%" 
    width="45%" 
    alt="AWS-WorkSpace-IAM-User-Project_4"
  />
</p>

---

### Step 3: Configure AWS WorkSpace
- Navigate to **WorkSpaces** in the AWS Console.
- Click **Launch WorkSpaces**.
- Choose the **Simple AD** created earlier.
- Add a user or select `jamie` if already synced from the directory.
- Choose a bundle:
  - **Type**: Standard with Windows 10 or Performance (depending on expected help desk load)
  - **Root Volume**: 80 GB
  - **User Volume**: 50 GB
- Launch the WorkSpace.


<p align="center">
  <img 
    src="https://github.com/user-attachments/assets/e317f1a9-0272-4311-956a-dbf4777a0f6b"
    height="45%" 
    width="45%" 
    alt="AWS-WorkSpace-IAM-User-Project_5"
  />
</p>

---

### Step 4: Assign and Email Login Info
- AWS will send an email to the user (`jamie`) with:
  - A **registration code**
  - A **download link** for the WorkSpaces client
- Use the client to log in and verify access.

---

## 🔐 Group Policy and Permissions

**Group Name**: `WorkSpacesUsers`  
**Attached Policies**:
- `AmazonWorkSpacesSelfServiceAccess`
- `AmazonWorkSpacesWebReadOnly`

**Optional**: Add a custom policy for scoped permissions and additional security control.

---

## 🧠 Lessons Learned

- IAM enables **secure and scalable access control** for user management.
- AWS WorkSpaces supports **hybrid workforces** with minimal infrastructure overhead.
- Predefined bundles and managed directories help **accelerate setup**.
- **Simple AD** is a cost-effective option for **small-scale environments**.



