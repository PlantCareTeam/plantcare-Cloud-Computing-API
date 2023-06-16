# PlantCare Backend Documentation

Welcome to the PlantCare Backend application documentation. PlantCare project aims to tackle the problem of crop failure caused by plant diseases by developing an easy-to-use mobile application. Our research questions focus on identifying plant diseases through visual recognition and providing appropriate treatment recommendations to help farmers and plant enthusiasts manage their crops efficiently and increase their yields.


## PlantCare Architecture Cloud
![Logo](https://github.com/PlantCareTeam/plantcare-Cloud-Computing-API/blob/main/PlantCare%20Architecture%20Cloud.jpg)

## List APi

## DOCUMENTATION API TERNAKU

### Authentication

#### Register

| Usage    | Endpoint                         |
| -------- | -------------------------------- |
| Register | POST /auth/register |

### **Example**

**parameters**

| Parameter    | Required | Deskripsi               |
| ------------ | -------- | ----------------------- |
| email        | Yes      | Alamat email pengguna   |
| password        | Yes      | Password email pengguna   |
| name        | Yes      | nama pengguna   |
- **Response:**
  - If successful:
      ```json
      {
    "error": false,
    "message": "Berhasil Register Akun. Silahkan Login"
    }
      ```
  - If email is already taken:
      ```json
      {
        "error": true,
        "message": "Email already taken"
      }
      ```

### **Login User**

| Usage    | Endpoint                      |
| -------- | ----------------------------- |
| Login | POST /auth/login |

### **Example**

**parameters**

| Parameter | Required | Deskripsi                   |
| --------- | -------- | --------------------------- |
| email     | Yes      | Email pengguna terdaftar    |
| password  | Yes      | Password pengguna terdaftar |

**result**
  - If successful:
      ```json
      {
    "error": false,
    "loginResult": {
        "email": "coba001@gmail.com",
        "name": "coba001",
        "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJmcmVzaCI6ZmFsc2UsImlhdCI6MTY4NjkxMjQyMywianRpIjoiNTliMTM2Y2QtOWJiNS00YzAwLWJkNzAtYmQ2MjY2NTRjNTZhIiwidHlwZSI6ImFjY2VzcyIsInN1YiI6MiwibmJmIjoxNjg2OTEyNDIzLCJleHAiOjE2ODcwODUyMjN9.XrABoE2h_MzIi1yJY5oMDzCU_Bwyn7piMCLqs7E4Y7Q",
        "userid": 2
    },
    "message": "Login Successed !"
    }
      ```
  - If email or password is incorrect:
      ```json
      {
        "error": true,
        "message": "Wrong Password or Account not found, please checked again"
      }
      ```
      
#### Dashboard

| Usage    | Endpoint                         |
| -------- | -------------------------------- |
| Dashboard | GET /Dasboard |

### **Example**

**parameters**

| Parameter    | Required | Deskripsi               |
| ------------ | -------- | ----------------------- |
| name        | Yes      | nama pengguna   |
- **Response:**
  - If successful:
      ```json
      Hallo! coba001
      ```
      
#### Profile

| Usage    | Endpoint                         |
| -------- | -------------------------------- |
| Profile | GET /Profile |

### **Example**

**parameters**

| Parameter    | Required | Deskripsi               |
| ------------ | -------- | ----------------------- |
| email        | Yes      | email pengguna   |
| name        | no      | nama pengguna   |
- **Response:**
  - If successful:
      ```json
      {
    "error": false,
    "profile": {
        "email": "coba001@gmail.com",
        "name": "coba001"
    }
    }
      ```
      
#### Logout

| Usage    | Endpoint                         |
| -------- | -------------------------------- |
| Logout | POST /Dasboard |

### **Example**

- **Response:**
  - If successful:
      ```json
        "error": true,
        "message": "Logout berhasil!"
      ```

#### History

| Usage    | Endpoint                         |
| -------- | -------------------------------- |
| History | GET /History |

### **Example**

**parameters**

| Parameter    | Required | Deskripsi               |
| ------------ | -------- | ----------------------- |
| User_id        | Yes      | user id pengguna   |
| Prediction_result        | Yes      | hasil prediksi pengguna   |
| Predict_id        | Yes      | id prediksi   |
| Plant_category        | Yes      | nama tumbuhan   |
| Image_url        | No      | url gambar tumbuhan   |
| Create_at        | Yes      | Tanggal prediksi dilakukan   |

- **Response:**
  - If successful:
      ```json
      [
    {
        "created_at": "Tue, 13 Jun 2023 17:42:06 GMT",
        "image_url": "https://storage.googleapis.com/plantcare-test/images/19ce773e-43de-4c3d-89a2-3effd3ec799e.jpg",
        "plant_category": "4",
        "predict_id": 1,
        "prediction_result": "Early Blight",
        "user_id": null
    },
    {
        "created_at": "Tue, 13 Jun 2023 21:46:28 GMT",
        "image_url": "https://storage.googleapis.com/plantcare-test/images/b1bdb289-08b4-432d-a893-e3d6273be902.jpg",
        "plant_category": "4",
        "predict_id": 2,
        "prediction_result": "Early Blight",
        "user_id": null
    },
    {
        "created_at": "Tue, 13 Jun 2023 22:02:11 GMT",
        "image_url": "https://storage.googleapis.com/plantcare-test/images/242ef7a5-510a-4282-99ee-7cdf8d374466.jpg",
        "plant_category": "4",
        "predict_id": 3,
        "prediction_result": "Early Blight",
        "user_id": null
    },
    {
        "created_at": "Tue, 13 Jun 2023 22:05:16 GMT",
        "image_url": "https://storage.googleapis.com/plantcare-test/images/f084a6b4-6fe0-4a97-9899-3cbd5a1ea5ba.jpg",
        "plant_category": "4",
        "predict_id": 4,
        "prediction_result": "Septoria Leaf Spot",
        "user_id": null
    },
    {
        "created_at": "Wed, 14 Jun 2023 11:32:21 GMT",
        "image_url": "https://storage.googleapis.com/plantcare-test/images/02a538c2-47c7-494a-9efa-23b4c7c01328.jpg",
        "plant_category": "4",
        "predict_id": 5,
        "prediction_result": "Target Spot",
        "user_id": 2
    },
    {
        "created_at": "Wed, 14 Jun 2023 11:39:58 GMT",
        "image_url": "https://storage.googleapis.com/plantcare-test/images/d21ee4dd-e7b8-48b4-9ec0-3c0f3cf240ca.jpg",
        "plant_category": "5",
        "predict_id": 6,
        "prediction_result": "Healthy",
        "user_id": 2
    },
    {
        "created_at": "Wed, 14 Jun 2023 11:41:32 GMT",
        "image_url": "https://storage.googleapis.com/plantcare-test/images/dad9972a-9c46-4b02-b488-357cd409375b.jpg",
        "plant_category": "5",
        "predict_id": 7,
        "prediction_result": "Powdery Mildew",
        "user_id": 2
    },
    {
        "created_at": "Wed, 14 Jun 2023 12:18:02 GMT",
        "image_url": "https://storage.googleapis.com/plantcare-test/images/01a94566-acb8-41c9-8f27-1e7f243ed472.jpg",
        "plant_category": "5",
        "predict_id": 8,
        "prediction_result": "Alternaria Leaf Spot",
        "user_id": 2
    },
    {
        "created_at": "Wed, 14 Jun 2023 12:19:19 GMT",
        "image_url": "https://storage.googleapis.com/plantcare-test/images/52315292-54d8-460f-87e9-49246588d3b4.jpg",
        "plant_category": "5",
        "predict_id": 9,
        "prediction_result": "Frogeye Leaf Spot",
        "user_id": 2
    },
    {
        "created_at": "Wed, 14 Jun 2023 12:20:01 GMT",
        "image_url": "https://storage.googleapis.com/plantcare-test/images/2a2f690f-0d13-4e01-a83d-ff68d6623b6a.jpg",
        "plant_category": "5",
        "predict_id": 10,
        "prediction_result": "Healthy",
        "user_id": 2
    },
    {
        "created_at": "Wed, 14 Jun 2023 12:26:17 GMT",
        "image_url": "https://storage.googleapis.com/plantcare-test/images/c892b4e1-f417-4cbc-8ad3-ffa191fd9b01.jpg",
        "plant_category": "5",
        "predict_id": 11,
        "prediction_result": "Apple scab",
        "user_id": 2
    },
    {
        "created_at": "Wed, 14 Jun 2023 12:29:41 GMT",
        "image_url": "https://storage.googleapis.com/plantcare-test/images/9f0cc909-aeb5-4acb-bf58-8a060276db20.jpg",
        "plant_category": "4",
        "predict_id": 12,
        "prediction_result": "Early Blight",
        "user_id": 2
    },
    {
        "created_at": "Wed, 14 Jun 2023 12:54:28 GMT",
        "image_url": "https://storage.googleapis.com/plantcare-test/images/ee6aa1ce-65b0-47e9-bf09-ba2f39ae5633.jpg",
        "plant_category": "4",
        "predict_id": 13,
        "prediction_result": "Bacterial Spot",
        "user_id": 2
    },
    {
        "created_at": "Wed, 14 Jun 2023 12:55:00 GMT",
        "image_url": "https://storage.googleapis.com/plantcare-test/images/0a615174-e564-46de-b73d-fe6f20205b2c.jpg",
        "plant_category": "4",
        "predict_id": 14,
        "prediction_result": "Healthy",
        "user_id": 2
    }
    ]
      ```
#### History by ID

| Usage    | Endpoint                         |
| -------- | -------------------------------- |
| History by ID| GET /historyid |

### **Example**

**parameters**

| Parameter    | Required | Deskripsi               |
| ------------ | -------- | ----------------------- |
| User_id        | Yes      | user id pengguna   |
| Prediction_result        | Yes      | hasil prediksi pengguna   |
| Predict_id        | Yes      | id prediksi   |
| Plant_category        | Yes      | nama tumbuhan   |
| Image_url        | No      | url gambar tumbuhan   |
| Create_at        | Yes      | Tanggal prediksi dilakukan   |

- **Response:**
  - If successful:
      ```json
      [
    {
        "created_at": "Wed, 14 Jun 2023 11:32:21 GMT",
        "image_url": "https://storage.googleapis.com/plantcare-test/images/02a538c2-47c7-494a-9efa-23b4c7c01328.jpg",
        "plant_category": "4",
        "predict_id": 5,
        "prediction_result": "Target Spot",
        "user_id": 2
    },
    {
        "created_at": "Wed, 14 Jun 2023 11:39:58 GMT",
        "image_url": "https://storage.googleapis.com/plantcare-test/images/d21ee4dd-e7b8-48b4-9ec0-3c0f3cf240ca.jpg",
        "plant_category": "5",
        "predict_id": 6,
        "prediction_result": "Healthy",
        "user_id": 2
    },
    {
        "created_at": "Wed, 14 Jun 2023 11:41:32 GMT",
        "image_url": "https://storage.googleapis.com/plantcare-test/images/dad9972a-9c46-4b02-b488-357cd409375b.jpg",
        "plant_category": "5",
        "predict_id": 7,
        "prediction_result": "Powdery Mildew",
        "user_id": 2
    },
    {
        "created_at": "Wed, 14 Jun 2023 12:18:02 GMT",
        "image_url": "https://storage.googleapis.com/plantcare-test/images/01a94566-acb8-41c9-8f27-1e7f243ed472.jpg",
        "plant_category": "5",
        "predict_id": 8,
        "prediction_result": "Alternaria Leaf Spot",
        "user_id": 2
    },
    {
        "created_at": "Wed, 14 Jun 2023 12:19:19 GMT",
        "image_url": "https://storage.googleapis.com/plantcare-test/images/52315292-54d8-460f-87e9-49246588d3b4.jpg",
        "plant_category": "5",
        "predict_id": 9,
        "prediction_result": "Frogeye Leaf Spot",
        "user_id": 2
    },
    {
        "created_at": "Wed, 14 Jun 2023 12:20:01 GMT",
        "image_url": "https://storage.googleapis.com/plantcare-test/images/2a2f690f-0d13-4e01-a83d-ff68d6623b6a.jpg",
        "plant_category": "5",
        "predict_id": 10,
        "prediction_result": "Healthy",
        "user_id": 2
    },
    {
        "created_at": "Wed, 14 Jun 2023 12:26:17 GMT",
        "image_url": "https://storage.googleapis.com/plantcare-test/images/c892b4e1-f417-4cbc-8ad3-ffa191fd9b01.jpg",
        "plant_category": "5",
        "predict_id": 11,
        "prediction_result": "Apple scab",
        "user_id": 2
    },
    {
        "created_at": "Wed, 14 Jun 2023 12:29:41 GMT",
        "image_url": "https://storage.googleapis.com/plantcare-test/images/9f0cc909-aeb5-4acb-bf58-8a060276db20.jpg",
        "plant_category": "4",
        "predict_id": 12,
        "prediction_result": "Early Blight",
        "user_id": 2
    },
    {
        "created_at": "Wed, 14 Jun 2023 12:54:28 GMT",
        "image_url": "https://storage.googleapis.com/plantcare-test/images/ee6aa1ce-65b0-47e9-bf09-ba2f39ae5633.jpg",
        "plant_category": "4",
        "predict_id": 13,
        "prediction_result": "Bacterial Spot",
        "user_id": 2
    },
    {
        "created_at": "Wed, 14 Jun 2023 12:55:00 GMT",
        "image_url": "https://storage.googleapis.com/plantcare-test/images/0a615174-e564-46de-b73d-fe6f20205b2c.jpg",
        "plant_category": "4",
        "predict_id": 14,
        "prediction_result": "Healthy",
        "user_id": 2
    }
    ]
      ```

#### Articles

| Usage    | Endpoint                         |
| -------- | -------------------------------- |
| articles | GET /articles |

### **Example**

**parameters**

| Parameter    | Required | Deskripsi               |
| ------------ | -------- | ----------------------- |
| Title        | Yes      | Judul dari artikel   |
| Content        | Yes      | Isi dari artikel   |
| img_url        | No      | gambar dari artikel   |


- **Response:**
  - If successful:
      ```json
      [
    {
        "Title": Tomato Plant ,
        "Content": "Tomat adalah tanaman tahunan yang berasal dari Amerika Selatan dan termasuk dalam keluarga Solanaceae. Tanaman tomat memiliki batang yang tegak dan daun hijau yang tersusun secara berselang-seling. Buah tomat biasanya berbentuk bulat atau oval dengan beragam warna seperti merah, kuning, hijau, atau oranye, tergantung pada varietasnya.\nTanaman tomat biasanya ditanam sebagai tanaman hortikultura dan merupakan salah satu tanaman pangan yang populer di seluruh dunia. Buah tomat kaya akan nutrisi, termasuk vitamin C, vitamin A, serat, dan likopen, yang memberikan manfaat kesehatan seperti meningkatkan sistem kekebalan tubuh, menjaga kesehatan jantung, dan mengurangi risiko beberapa jenis kanker.",
        "img_url": null,
    }
      ```
#### Articles by ID

| Usage    | Endpoint                         |
| -------- | -------------------------------- |
| articles by id | GET /articles/id |

### **Example**

**parameters**

| Parameter    | Required | Deskripsi               |
| ------------ | -------- | ----------------------- |
| Title        | Yes      | nama pengguna   |
| Content        | Yes      | nama pengguna   |
| img_url        | Yes      | nama pengguna   |


- **Response:**
  - If successful:
      ```json
      [
    {
        "Title": Tomato Plant ,
        "Content": "Tomat adalah tanaman tahunan yang berasal dari Amerika Selatan dan termasuk dalam keluarga Solanaceae. Tanaman tomat memiliki batang yang tegak dan daun hijau yang tersusun secara berselang-seling. Buah tomat biasanya berbentuk bulat atau oval dengan beragam warna seperti merah, kuning, hijau, atau oranye, tergantung pada varietasnya.\nTanaman tomat biasanya ditanam sebagai tanaman hortikultura dan merupakan salah satu tanaman pangan yang populer di seluruh dunia. Buah tomat kaya akan nutrisi, termasuk vitamin C, vitamin A, serat, dan likopen, yang memberikan manfaat kesehatan seperti meningkatkan sistem kekebalan tubuh, menjaga kesehatan jantung, dan mengurangi risiko beberapa jenis kanker.",
        "img_url": null,
    }
    ]
      ```      

#### Predict Tomato

| Usage    | Endpoint                         |
| -------- | -------------------------------- |
| predict tomato | POST /predict-tomat |

### **Example**

**parameters**

| Parameter    | Required | Deskripsi               |
| ------------ | -------- | ----------------------- |
| image        | Yes      | gambar tanaman yang ingin dideteksi   |


- **Response:**
  - If successful:
      ```json
      {
    "deskripsi": {
        "description": "Dicirikan dengan batang tomat yang tumbuh rambut-rambut halus diseluruh permukaannya, daun yang berwarna hijau, berambut, dan mempunyai panjang sekitar 30 cm dan lebar 20 cm, bunga tomat berwarna kuning cerah, buah yang masih muda berwarna hijau muda sampai hijau tua.",
        "pengobatan": "Tidak memerlukan pengobatan, cukup dirawat seperti biasa secara rutin",
        "penyebab": "Sehat Secara Keseluruhan Tumbuhan",
        "rekomendasi_obat": "Tidak ada"
    },
    "image_hex": "https://storage.googleapis.com/plantcare-test/images/c62a7cb3-2d97-4c2b-9f5b-507981a6dbc9.jpg",
    "predicted_label": "Healthy"
    }
      ```
      
#### Predict Apple

| Usage    | Endpoint                         |
| -------- | -------------------------------- |
| predict apple | POST /predict-apple |

### **Example**

**parameters**

| Parameter    | Required | Deskripsi               |
| ------------ | -------- | ----------------------- |
| image        | Yes      | gambar tanaman yang ingin dideteksi   |


- **Response:**
  - If successful:
      ```json
      {
    "deskripsi": {
        "description": "Penyakit ini ditandai dengan bercak putih seperti beludru di bagian bawah daun dan pucuk, serta bintik-bintik klorosis di bagian atas daun.",
        "pengobatan": "Pencegahan dapat dilakukan dengan menanam jenis apel yang kurang rentan atau memiliki resistansi terhadap beberapa penyakit. Hal tersebut dapat mengurangi penggunaan fungisida dan jumlah buaya dari program penyemprotan selama masa pertumbuhan. Infeksi primer dapat dikontrol dengan membuang sumber inokulum primer. Pangkaslah seluruh puncuk terminal yang memutih selama musim dingin atau di awal musim semi. Infeksi sekunder dan infeksi buah dapat dikontrol dengan pengaplikasian fungisida.",
        "penyebab": "Penyakit ini disebabkan oleh jamur (Podosphaera leucotricha). Spora jamur ini hidup dalam tunas selama musim dingin dan biasanya menyebar melalui angin. ",
        "rekomendasi_obat": "Metode yang dapat diterima secara organik adalah penanganan dengan lime and sulfur, sulfur only, dan minyak hotikiltural. "
    },
    "image_hex": "https://storage.googleapis.com/plantcare-test/images/664ef89b-fea3-44b8-a752-0e13c682fdfd.jpg",
    "predicted_label": "Powdery Mildew"
    }
      ```
      
## Running the Application

To run PlantCare backend application, execute the following command:

```shell
python main.py
```

The application will start running on `http://localhost:127.0.0.1:8080/`.

Make sure you have the required dependencies installed and the necessary configurations set before running the application.

That's it! You have successfully set up and documented the Ternaku backend application.

## Disclaimer
-   This project is created for educational purpose as the requirement to graduate from [**_Bangkit Academy led by Google, Tokopedia, Gojek, & Traveloka_**.](https://www.linkedin.com/company/bangkit-academy/mycompany/)

# Thank You so Much :)
