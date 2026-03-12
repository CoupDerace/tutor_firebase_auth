# tutor_firebase_auth
## Step by step Firebase Console
## 1. Login ke Firebase Console dan Membuat Project

Buka website Firebase Console
   https://console.firebase.google.com/u/0/
   
Login menggunakan akun Google
<img width="940" height="473" alt="image" src="https://github.com/user-attachments/assets/f08b539d-7d44-40af-b3d6-533768e937aa" />

Klik **Create New Project**
<img width="940" height="450" alt="image" src="https://github.com/user-attachments/assets/8267bcae-933b-4c1c-be4c-83941bc038bc" />

Selanjutnya klik continue sampai menemukan halaman ini
<img width="940" height="453" alt="image" src="https://github.com/user-attachments/assets/52ac78e4-056e-422d-911a-ea3461a46afb" />

Jika sudah menemukan yg Google Analytic ini kalian bisa nonaktifkan, lalu klik create project
<img width="940" height="449" alt="image" src="https://github.com/user-attachments/assets/851386ca-f139-4ec3-b85b-71d7558bd263" />

Tunggu hingga selesai
<img width="940" height="448" alt="image" src="https://github.com/user-attachments/assets/af5127be-2654-45fd-824b-6f1e83acd768" />

Jika hasilnya seperti ini berarti kalian sudah berhasil membuat firebase project baru, klik continue
<img width="940" height="472" alt="image" src="https://github.com/user-attachments/assets/ac1e2f44-820c-4873-9fbe-db806f664c14" />

Lalu akan muncul project kalian, kalian bisa klik saja projectnya
<img width="940" height="468" alt="image" src="https://github.com/user-attachments/assets/9842b653-d538-49c8-95a1-037491def7c8" />

Jika sudah, kalian bisa klik + Add app
<img width="844" height="234" alt="image" src="https://github.com/user-attachments/assets/00a53995-4f18-414d-a17c-23b7bda69870" />

Kalian klik yang Web
<img width="940" height="450" alt="image" src="https://github.com/user-attachments/assets/81ba8714-a36e-460f-91d9-b1d5674ce652" />

Lalu ketik saja App nickname kalian, lalu Register app ( tidak perlu centang bawahnya )
<img width="940" height="456" alt="image" src="https://github.com/user-attachments/assets/41367337-5e66-4e5c-bfe9-4329957f4d50" />

Lalu kalian simpan atau salin code diatas yang berisi apiKey dll, lalu klik continue to console
<img width="940" height="466" alt="image" src="https://github.com/user-attachments/assets/762f9082-4398-47cf-b87c-e29b4dadfcc4" />

Nah, disini sudah muncul 1 app punya kalian, lalu kalian buka sidebar nya
<img width="230" height="637" alt="image" src="https://github.com/user-attachments/assets/38502f75-ec47-4015-a1b0-6e5e9472a4d6" />

Klik project overview, lalu cari Authentication yang terletak pada Security, jika sudah kalian klik Sign In method
<img width="940" height="471" alt="image" src="https://github.com/user-attachments/assets/85b05b5f-2fbc-4488-a392-a49b75433310" />

Lalu klik Email/Password
<img width="940" height="349" alt="image" src="https://github.com/user-attachments/assets/246300a3-677c-40f7-959d-b586062d4dff" />

Ikuti pada gambar lalu klik save
<img width="940" height="140" alt="image" src="https://github.com/user-attachments/assets/19443577-adcd-4ba1-aad2-ccf36da7a4d2" />
Disini kalian sudah memiliki satu provider dan kalian juga bisa tambah sesuka kalian.

## Kita masuk ke apk Postman.
Disini kita bikin Environment baru, dan tambahkan variable seperti berikut
<img width="940" height="499" alt="image" src="https://github.com/user-attachments/assets/0a808fea-e2a2-4e0d-b545-c3b21d693fd5" />

Lakukan secara manual ( ketik ), lalu kita ambil apiKey yang tadi kita simpan, lalu salin pada bagian value, lalu kalian ketik Email dan Password kalian, lalu buatlah regist akun dengan metode POST
<img width="119" height="259" alt="image" src="https://github.com/user-attachments/assets/a5a34c08-c433-497b-a20e-268dcce26526" />
<img width="940" height="332" alt="image" src="https://github.com/user-attachments/assets/4bb1c389-8456-4ea9-9c8d-c70cc6222c43" />

https://identitytoolkit.googleapis.com/v1/accounts:signUp?key={{FIREBASE_API_KEY}}

ini untuk URL nya yang akan kita kirim, pastikan {{FIREBASE_API_KEY}}, {{USER_EMAIL}}
dan {{USER_PASSWORD}} sesuai dengan yang ada di Environment tadi
<img width="940" height="343" alt="image" src="https://github.com/user-attachments/assets/4c857ad9-317d-41ec-86b6-6d2b0683d2ea" />
Ini untuk bagian Headers nya
 
<img width="940" height="339" alt="image" src="https://github.com/user-attachments/assets/9e99b4d4-1886-474e-bfae-19960988b492" />
Dan ini untuk Paramsnya

<img width="940" height="347" alt="image" src="https://github.com/user-attachments/assets/2be54f35-69f8-4978-abec-f9220e455421" />
Lalu tambahkan code ini pada bagian Script yang bertujuan agar idToken tersimpan otomatis, lalu kita bisa klik SEND.
<img width="940" height="593" alt="image" src="https://github.com/user-attachments/assets/e80fd8e6-a642-41cb-a3e0-8ae2f0c49fe0" />

Jika berhasil, maka akan muncul idToken yang nantinya akan tersimpan otomatis di Environment 
<img width="940" height="291" alt="image" src="https://github.com/user-attachments/assets/e7e3c3ab-6bf7-4065-be69-0761709ff0ba" />

Setelah itu kita coba akan lakukan pengiriman email dengan URL berikut
https://identitytoolkit.googleapis.com/v1/accounts:sendOobCode?key={{FIREBASE_API_KEY}}
<img width="940" height="323" alt="image" src="https://github.com/user-attachments/assets/0c0fad14-25d0-4d37-b1ca-95bd429ba5fb" />

Pastikan pada {{FIREBASE_API_KEY}} dan {{FIREBASE_ID_TOKEN}}
Sesuai dengan yang ada di Environment kalian

<img width="940" height="340" alt="image" src="https://github.com/user-attachments/assets/85e0c106-3825-4a2a-bb67-cec31697497f" />
Untuk Headers

<img width="940" height="344" alt="image" src="https://github.com/user-attachments/assets/871c5d5c-bf4f-4da8-ae69-3d96036221a7" />
Untuk params, lalu kita bisa klik SEND

<img width="940" height="565" alt="image" src="https://github.com/user-attachments/assets/62ec0fe6-b157-413e-92e9-b13c7a33a32b" />
Jika muncul seperti ini tandanya kalian berhasil mengirim pesan ke Email tersebut

Kalian bisa cek pada Firebase Authentication kalian bahwa kalian telah berhasil mengirim pesan ke Email tersebut, lalu kalian cek juga pada email kalian di bagian spam 
<img width="940" height="448" alt="image" src="https://github.com/user-attachments/assets/719ba4ad-a520-4e06-b61a-becf94e8aa0b" />
<img width="940" height="446" alt="image" src="https://github.com/user-attachments/assets/e17307e9-0171-45d8-8e16-3553a962626a" />
<img width="940" height="443" alt="image" src="https://github.com/user-attachments/assets/8850f71e-93d9-49a2-a3c5-a012a6a46970" />
Dan kalian berhasil mengirimkan pesan ke email kalian 





