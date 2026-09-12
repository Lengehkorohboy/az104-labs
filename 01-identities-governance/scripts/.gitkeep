# Lab 01 - Manage Microsoft Entra ID Identities

## Overview

This lab is part of my AZ-104: Microsoft Azure Administrator learning journey.
This lab focuses on managing identities in Microsoft Entra ID.
The goal is to understand how to create and manage users, groups, administrative units, and role assignments within a Microsoft Entra tenant

## Learning Objectives

By completing this lab, I was able to:
Create and manage Microsoft Entra users
Create and manage security groups
Configure group membership
Assign built-in administrative roles
Manage administrative units
Review identity management best practices

## Skills Covered

Microsoft Entra ID Administration
Identity and Access Management (IAM)
User Lifecycle Management
Group Management
Administrative Roles
Azure Portal Navigation
RBAC Fundamentals

## Azure Services Used

Microsoft Entra ID
Azure Portal

## Architecture Diagram

Microsoft Entra ID Tenant
│
├── Users
│ ├── az104-labuser1
│ └── az104-labuser2
│
├── Groups
│ └── IT Lab Administrators

## Prerequisites

Before starting this lab:
Active Azure Subscription
Contributor Permissions
Azure CLI Installed

## Lab Environment

Item Value
Service Microsoft Entra ID
Portal https://portal.azure.com
Region Global Service
Identity Type Cloud-Only Users

## Tasks

### Task 1: Create Users

#### Objective

Create cloud-based user accounts within Microsoft Entra ID.

#### Azure Portal Steps

1. Sign in to Azure Portal - `https://portal.azure.com`
2. Navigate to Microsft Entra ID
3. Select Users
4. Click on New User
5. Create two user accounts
6. Review + Create

### Example Users

az104-labusers1 az104-labuser1
az104-labusers2 az104-labuser2

### Validation

User az104-labusers1 az104-labuser1 and az104-labusers2 az104-labuser2 successfully created

![Screenshot of create Users.](../01-identities-governance/Screenshots/Create%20Users.png)

## Task 2: Create Security Groups

### Objective

Create a security group to manage permissions collectively

### Azure Portal Steps

1. Navigate to Groups
2. Select New Group
3. Group Type: Security
4. Group Name: IT Lab Administrators
5. Create Group

### Validation

IT Lab Administrators Security Group successfully created

![Screenshot of create Users.](../01-identities-governance/Screenshots/Create%20Group.png)

## Task 3: Add Group Members

### Objective

Assign Users to the Security Group

### Azure Portal Steps

1. Navigate to Groups
2. Open IT Lab Administrators group
3. Select members
4. Select Add memebers
5. Add az104-labuser1 and az104-labuser2 accounts
6. Save

### Validation

az104-labuser1 and az104-labuser2 added successfully

![Screenshot of Assign users to IT Lab Administrators group](../01-identities-governance/Screenshots/Add%20user%20to%20group.png)

## Task 4 - Assign Administrative Roles

### Objective

Grant administrator permissions using least privilege principles.

### Azure Portal Steps

Navigate to Roles and Administrators
Select User Administrator
Add Assignment
Assign role to az104-labuser1 and az104-labuser2

### Validation

User Administrator role assigned to az104-labuser1 and az104-labuser2

![Screenshot of assigning administrator role](../01-identities-governance/Screenshots/Administrator%20permission.png)

## Task 5: Create an Administrative Unit

### Objective

Delegate administration of a subset of users

### Azure Portal Steps

Open Administrative Units
Select Add
Create: Marketin-Users

### Key Takeaways

Identity Management
Users are the foundation of Microsoft Entra ID.
Groups simplify access management.
Administrative roles should follow least-privilege principles.
Security Best Practices
Assign permissions through groups when possible.
Regularly review role assignments.
Use Administrative Units for delegated administration.
Avoid assigning Global Administrator unnecessarily.

### Lesson Learned

User not appearing in group.

### Resolution

Allow time for directory synchronization and refresh the portal.

### Resources

Manage users and groups in Microsoft Entra ID
https://learn.microsoft.com/training/modules/create-users-and-groups-in-azure-active-directory/

Manage Azure identities and governance (AZ-104 Learning Path)
https://learn.microsoft.com/training/paths/az-104-manage-identities-governance/

### Lab Status

✅ Completed

Date Completed: 2026-09-12

Estimated Duration: 30-45 Minutes

Certification Domain: Manage Azure Identities and Governance (AZ-104)
