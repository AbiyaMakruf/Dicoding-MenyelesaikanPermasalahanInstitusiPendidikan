# Proyek Akhir: Menyelesaikan Permasalahan Perusahaan Edutech

## Business Understanding
**Jaya Jaya Institut** adalah sebuah institusi pendidikan tinggi yang telah berdiri sejak tahun 2000. Selama lebih dari dua dekade, institusi ini telah berhasil mencetak banyak lulusan dengan reputasi yang sangat baik di berbagai bidang. Namun, seperti banyak institusi pendidikan lainnya, Jaya Jaya Institut juga menghadapi tantangan yang signifikan terkait dengan tingginya tingkat siswa yang tidak menyelesaikan pendidikannya alias dropout.

**Masalah dropout** ini merupakan masalah yang serius bagi institusi pendidikan, karena dropout yang tinggi dapat mempengaruhi citra institusi, mengurangi tingkat kelulusan, dan pada akhirnya berdampak pada daya tarik institusi bagi calon siswa di masa mendatang. Tingkat dropout yang tinggi juga bisa menjadi indikasi bahwa ada masalah mendasar dalam proses penerimaan siswa, pembelajaran, atau dukungan akademik yang disediakan oleh institusi.

### Permasalahan Bisnis
Berikut adalah beberapa pertanyaan yang menggambarkan permasalahan bisnis yang akan diselesaikan oleh Jaya Jaya Institut:

1. Bagaimana cara mengidentifikasi siswa-siswa yang berpotensi mengalami dropout sejak dini?
2. Faktor-faktor apa saja yang paling berpengaruh terhadap keputusan siswa untuk dropout?
3. Apa yang dapat dilakukan untuk meningkatkan tingkat retensi siswa dan memastikan lebih banyak siswa menyelesaikan pendidikan mereka?

### Cakupan Proyek
* Analisis Data: Menggunakan data yang ada untuk mengidentifikasi faktor-faktor utama yang mempengaruhi dropout.
* Visualisasi & Pelaporan: Mengembangkan dashboard yang dapat digunakan untuk memonitor dan menganalisis faktor-faktor tersebut secara visual.
* Rekomendasi & Intervensi: Berdasarkan hasil analisis, memberikan rekomendasi untuk intervensi yang dapat dilakukan untuk mengurangi droput.

### Persiapan

Sumber data: dataset yang digunakan merupakan dataset [Jaya Jaya Institut](https://github.com/dicodingacademy/dicoding_dataset/tree/main/students_performance).

* Setup environment:
    ```
    conda create --name proyek-institusi-pendidikan python==3.9.15
    ```
* Install requirements: 
    ```
    pip install -r requirements.txt
    ```
* Setup metabase:
    ```
    docker pull metabase/metabase:v0.46.4
    docker run -p 3000:3000 --name metabase metabase/metabase
    ```
    Akses metabase pada http://localhost:3000/setup dan lakukan setup.
* Setup database (supabase):

    * Buat akun dan login https://supabase.com/dashboard/sign-in.
    * Buat new project
    * Copy URI pada database setting
    * Kirim dataset menggunakan sqlalchemy 
    ```python
    from sqlalchemy import create_engine
 
    URL = "DATABASE_URL"
    
    engine = create_engine(URL)
    df.to_sql('dataset', engine)
    ```

## Business Dashboard
Jelaskan tentang business dashboard yang telah dibuat. Jika ada, sertakan juga link untuk mengakses dashboard tersebut.

## Menjalankan Sistem Machine Learning
Jelaskan cara menjalankan protoype sistem machine learning yang telah dibuat. Selain itu, sertakan juga link untuk mengakses prototype tersebut.

Pada proyek ini telah disediakan sebuah prototype untuk melakukan prediksi terhadap model yang sudah dibuat. Untuk menjalankan protoype secara lokal jalankan perintah berikut di terminal: 
    ```
        streamlit run app.py
    ```

Atau buka [tautan](https://dicoding-menyelesaikanpermasalahaninstitusipendidikan-5v4ahztm.streamlit.app/) untuk membuka prototype yang sudah dijalankan pada streamlit community.

<img src="https://raw.githubusercontent.com/AbiyaMakruf/Dicoding-MenyelesaikanPermasalahanInstitusiPendidikan/main/images/prototype.png" width="500">

## Conclusion
Proyek ini dirancang untuk menjawab beberapa permasalahan utama yang dihadapi oleh Jaya Jaya Institut terkait dengan tingkat dropout siswa. Berikut adalah kesimpulan dari proyek ini:

1. Bagaimana cara mengidentifikasi siswa-siswa yang berpotensi mengalami dropout sejak dini?
    - Dengan membangun model prediktif menggunakan algoritma seperti Random Forest, Jaya Jaya Institut dapat mengidentifikasi siswa-siswa yang berpotensi mengalami dropout sejak dini. Model ini mampu mendeteksi siswa berisiko dengan tingkat akurasi yang memadai berdasarkan data historis dan faktor-faktor demografis, akademik, serta ekonomi.

2. Faktor-faktor apa saja yang paling berpengaruh terhadap keputusan siswa untuk dropout?
    - Analisis korelasi dan pentingnya fitur dalam model prediktif menunjukkan bahwa beberapa faktor yang paling berpengaruh terhadap keputusan siswa untuk dropout antara lain latar belakang akademik (seperti nilai dan jumlah unit yang diambil) dan kondisi ekonomi (scholarship ataupun displaced) . Misalnya, siswa yang menghadapi kesulitan akademik dalam semester pertama atau kedua cenderung memiliki risiko lebih tinggi untuk dropout.

    <img src="https://raw.githubusercontent.com/AbiyaMakruf/Dicoding-MenyelesaikanPermasalahanInstitusiPendidikan/main/images/korelasi.png" width="500">
    
3. Apa yang dapat dilakukan untuk meningkatkan tingkat retensi siswa dan memastikan lebih banyak siswa menyelesaikan pendidikan mereka?
    - Berdasarkan temuan dari model dan analisis data, Jaya Jaya Institut dapat meningkatkan tingkat retensi siswa dengan beberapa strategi, seperti menyediakan bimbingan akademik yang lebih intensif, menyesuaikan kurikulum untuk mengurangi beban siswa, dan memberikan dukungan finansial tambahan kepada siswa yang membutuhkannya. Intervensi yang lebih dini dan berbasis data dapat membantu memastikan lebih banyak siswa menyelesaikan pendidikan mereka.

### Rekomendasi Action Items
Berikan beberapa rekomendasi action items yang harus dilakukan perusahaan guna menyelesaikan permasalahan atau mencapai target mereka.
1. Implementasi Sistem Pemantauan Siswa Berbasis Data
    - Menerapkan model prediktif yang telah dibangun untuk memantau siswa secara berkala. Institusi dapat menggunakan sistem ini untuk mendeteksi siswa yang berisiko tinggi untuk dropout dan memberikan intervensi dini berupa bimbingan akademik atau dukungan lainnya.
2. Pengembangan Program Dukungan Akademik dan Psikologis
    - Berdasarkan faktor-faktor risiko yang diidentifikasi, institusi harus memperkuat program dukungan akademik dan psikologis. Ini bisa mencakup peningkatan akses ke bimbingan belajar, sesi konseling, dan dukungan kesehatan mental bagi siswa yang rentan.
3. Optimalisasi Kurikulum dan Program Studi
    - Lakukan evaluasi terhadap program studi yang memiliki tingkat dropout tinggi dan lakukan penyesuaian kurikulum atau metode pengajaran. Misalnya, meningkatkan fleksibilitas dalam penjadwalan kursus atau menyediakan materi pendukung tambahan dapat membantu mengurangi tekanan akademik pada siswa.


Username: root@mail.com Password: root123