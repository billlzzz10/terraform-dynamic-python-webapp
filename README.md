# 🚀 terraform-dynamic-python-webapp

โมดูล Terraform สร้างเว็บ Python อัตโนมัติบน Google Cloud  
**Deploy ได้ทั้ง Dynamic Web, Static Site, เชื่อมต่อ Cloud Run, Cloud SQL, Firebase Hosting และอื่น ๆ ในคลิกเดียว**

---

## 🎯 ไฮไลต์สำคัญ

- **สร้าง-จัดการเว็บ Python ได้ยืดหยุ่น**  
- รองรับ Cloud Run, Cloud SQL, Secret Manager, IAM, Storage
- Deploy Static Web ขึ้น Firebase Hosting ได้ทันที
- ใช้งานง่าย ปลอดภัย เหมาะกับทุกทีม ทุกสายงาน
- ตัวอย่างโค้ดอ่านง่าย เหมาะกับสายภาวะสมาธิสั้น

---

## 🛠️ วิธีใช้งานด่วน

1. **เตรียม Google Cloud Project เปิด Billing ให้พร้อม**
2. **เพิ่มโมดูลลงในโค้ด Terraform ของคุณ**
   ```hcl
   module "dynamic-python-webapp" {
     source     = "."
     project_id = var.project_id
   }
   ```
3. **ดูตัวอย่างการใช้งาน**  
   ที่โฟลเดอร์ [examples](./infra/examples/)

---

## 🚦 บริการที่โมดูลนี้ดูแลให้

- Cloud Run (แอป Python แบบ serverless)
- Cloud SQL (ฐานข้อมูล)
- Firebase Hosting (เว็บ static)
- Secret Manager (เก็บ API key อย่างปลอดภัย)
- IAM (จัดการสิทธิ์)
- Cloud Storage (เก็บไฟล์)

---

## 💡 ข้อกำหนดเบื้องต้น

### โปรแกรมที่ต้องมี
- [Terraform](https://www.terraform.io/downloads.html) v0.13+
- [Terraform GCP Provider](https://www.terraform.io/docs/providers/google/index.html) v3.0+

### Service Account ต้องมีสิทธิ์
<details>
<summary>คลิกดูรายการ <strong>Google Cloud IAM Roles</strong></summary>

- roles/cloudbuild.builds.editor  
- roles/cloudsql.admin  
- roles/compute.admin  
- roles/compute.networkAdmin  
- roles/firebase.managementServiceAgent  
- roles/firebasehosting.admin  
- roles/iam.serviceAccountAdmin  
- roles/iam.serviceAccountUser  
- roles/pubsub.editor  
- roles/resourcemanager.projectIamAdmin  
- roles/run.admin  
- roles/secretmanager.admin  
- roles/storage.admin  
</details>

### เปิด API เหล่านี้ใน Google Cloud
<details>
<summary>คลิกดูรายการ <strong>API ที่ต้องเปิดใช้</strong></summary>

- run.googleapis.com  
- iam.googleapis.com  
- artifactregistry.googleapis.com  
- compute.googleapis.com  
- sql-component.googleapis.com  
- cloudbuild.googleapis.com  
- secretmanager.googleapis.com  
- firebase.googleapis.com  
- config.googleapis.com  
- cloudresourcemanager.googleapis.com  
- sqladmin.googleapis.com  
</details>

---

## 📦 Output ที่จะได้รับ

| ชื่อ            | คำอธิบาย           |
|-----------------|--------------------|
| firebase_url    | URL เว็บไซต์ Firebase |

---

## 🔗 ลิงก์แนะนำ

- [Hosting Static Website (Google Cloud)](https://cloud.google.com/storage/docs/hosting-static-website)
- [ตัวอย่างการใช้งาน (infra/examples)](./infra/examples/)
- [Project Factory Module](https://registry.terraform.io/modules/terraform-google-modules/project-factory/google)
- [IAM Module](https://registry.terraform.io/modules/terraform-google-modules/iam/google)

---

## 🤝 ร่วมพัฒนา & แจ้งปัญหา

- อ่าน [Contribution Guidelines](CONTRIBUTING.md) ก่อนร่วมโค้ด
- แจ้งช่องโหว่ความปลอดภัยที่ [Security Disclosure Process](SECURITY.md)

---