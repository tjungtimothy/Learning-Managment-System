# 🎓 Advanced-LMS

A modern, full-stack **Learning Management System (LMS)** designed for scalability, performance, and real-world usage. Built with **Node.js, Express, MongoDB, React**, and **Cloudinary** for seamless video hosting.

---

## ✨ Highlights

* 🔐 Secure authentication with **JWT** (Student & Educator roles)
* 👨‍🏫 Educators can **create, publish, and manage** courses
* 👨‍🎓 Students can **enroll, purchase, and track progress**
* 🎥 High-quality **video upload & streaming** via Cloudinary
* ⭐ Course **ratings & reviews** system
* 📊 Per-course **progress tracking**
* 🧱 Clean **RESTful API** architecture

---


---

## 🧰 Tech Stack

**Backend**

* Node.js
* Express.js
* MongoDB + Mongoose

**Frontend**

* React (located in `/client`)

**Media & Auth**

* Cloudinary (Video Hosting)
* JWT & bcrypt (Authentication)

---


### 2️⃣ Install Backend Dependencies

```bash
cd server
npm install
```

### 3️⃣ Environment Setup

Create a `.env` file inside `/server`:

```env
MONGODB_URI=your_mongodb_uri
PORT=3000
JWT_TOKEN=your_jwt_secret
CLOUDINARY_NAME=your_cloudinary_name
CLOUDINARY_API_KEY=your_cloudinary_api_key
CLOUDINARY_SECRET_KEY=your_cloudinary_secret
```

### 4️⃣ Start Backend Server

```bash
npm start
```

### 5️⃣ Start Frontend (Optional)

```bash
cd ../client
npm install
npm run dev
```

---

## 🔌 API Overview

### 🔑 Authentication

* `POST /api/auth/register` – Register user
* `POST /api/auth/login` – Login user
* `POST /api/auth/logout` – Logout user

### 👤 User

* `GET /api/user/profile` – Get profile
* `POST /api/user/enroll/:courseId` – Enroll in course
* `POST /api/user/purchase/:courseId` – Purchase course
* `PUT /api/user/progress/:courseId` – Update progress
* `GET /api/user/progress/:courseId` – Get progress
* `POST /api/user/rating/:courseId` – Rate course

### 📚 Course

* `GET /api/course/all` – All published courses
* `POST /api/course/create` – Create course (Educator)
* `DELETE /api/course/:courseId` – Delete course
* `GET /api/course/my-courses` – Educator courses
* `PATCH /api/course/:courseId/toggle-publish` – Publish/Unpublish
* `POST /api/course/enroll/:courseId` – Enroll (Student)

### 📖 Chapter

* `GET /api/chapter/course/:courseId` – Course chapters
* `POST /api/chapter/create/:courseId` – Create chapter
* `DELETE /api/chapter/:chapterId` – Delete chapter

### 🎬 Lecture

* `GET /api/lecture/chapter/:chapterId` – Chapter lectures
* `POST /api/lecture/create/:courseId/:chapterId` – Create lecture
* `DELETE /api/lecture/:lectureId` – Delete lecture

### 🎥 Video

* `POST /api/video/upload` – Upload video (Educator)

---

## ☁️ Video Upload Notes

* Videos are uploaded using **Cloudinary**
* Managed via `multer` (size configurable)
* Use returned `videoUrl` when creating lectures

---

## 📄 License

This project is licensed under the **MIT License**.

---

### 👨‍💻 Maintained by **Timothy**

If you like this project, ⭐ star the repo and feel free to contribute!
