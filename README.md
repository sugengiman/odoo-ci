# odoo-ci

## 🚀 Apa yang Dilakukan Workflow Ini?

Saat ada **push ke `main`**, pipeline akan menjalankan:

1. **Static Code Analysis**
   - Linting Python menggunakan `ruff`
2. **Unit Test**
   - Menjalankan `pytest`
3. **Integration Test**
   - Test koneksi ke PostgreSQL
4. **Build Docker Image**
   - Build image Odoo menggunakan Docker
5. **End-to-End Test**
   - Menjalankan container Odoo
   - Mengecek halaman login Odoo
6. **Push Image ke AWS ECR**
7. **Deploy ke AWS ECS**
   - Menggunakan `force-new-deployment`

---

## 🧱 Alur Sederhana

GitHub Push / PR
↓
Lint & Test
↓
Build Docker Image
↓
E2E Test (Odoo)
↓
Push ke ECR
↓
Deploy ke ECS


---

## 📁 File Penting

.github/workflows/odoo-ci.yml # Workflow GitHub Actions
Dockerfile # Docker image Odoo


---

## 🔐 GitHub Secrets yang Dibutuhkan

Tambahkan secrets berikut di repository GitHub:

- `AWS_ACCESS_KEY_ID`
- `AWS_SECRET_ACCESS_KEY`
- `AWS_REGION`
- `ECR_REPO`
- `ECS_CLUSTER`
- `ECS_SERVICE`

---

## 👨‍💻 Author

Sugeng Iman Santosa 
