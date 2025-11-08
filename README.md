# analisis-nilai-siswa

## Langkah-langkah Analisis


1. **Import Library**
   ```python
   import pandas as pd
   import matplotlib.pyplot as plt
   import seaborn as sb
   ```

2. **Membaca File CSV**
   ```python
   data = pd.read_csv('nilai_siswa.csv')
   data.info()
   data.head()
   data.describe()
   ```

3 **Menampilkan Statistik Dasar**
   ```python
   print("Rata-rata:", data['Nilai'].mean())
   print("Median:", data['Nilai'].median())
   print("Modus:", data['Nilai'].mode()[0])
   ```
4. **Memisahkan Data Per Mapel**
   ```python
   matematika = data[data['Matpel'] == 'Matematika']
   produktif = data[data['Matpel'] == 'Produktif']
   inggris = data[data['Matpel'] == 'Bahasa Inggris']
   indo = data[data['Matpel'] == 'Bahasa Indonesia']
   fisika = data[data['Matpel'] == 'Fisika']
   ```
5. **Mengelompokan Data & Menghitung Rata-Rata**
   ```python
   rata = data.groupby('Matpel')['Nilai'].mean()
   print(rata)
   ```
6. **Mebuat Grafik Batang**
   ```python
   rata.plot(kind='bar')
   plt.title('Rata-rata Nilai per Mapel')
   plt.xlabel('Mata Pelajaran')
   plt.ylabel('Nilai Rata-rata')
   plt.show()
   ```
7. **Membuat Boxplot**
   ```python
   sb.boxplot(x='Matpel', y='Nilai', data=data)
   plt.title('Sebaran Nilai per Mata Pelajaran')
   plt.show()
   ```
8. **Analisis**
    ```python
    Analisis dan Pertanyaan
   1. Mapel mana yang memiliki rata-rata nilai tertinggi?
   == Fisika
   2. Mapel mana yang memiliki nilai terendah?
   == Bahasa Indonesia
   3. Bagaimana visualisasi membantu dalam memahami data?
   == visualisasi dapat membantu melihat perbandig=ngan nilai antar matpel dengan cepat
    ```
9. **Refleksi**
    ```python
   Refleksi Siswa
   1. Apa hal baru yang kamu pelajari dari kegiatan analisis dan visualisasi data?
   == saya belajar cara menggunakan pandas unutk membaca dan mengelompokan data,menghitung rata rata dll,serta menggunakan matplotlib dan seaborn agar data kebih mudah dipahami
   2. Kesulitan apa yang kamu alami dalam membuat grafik?
   == kurang teliti sehingga banyak sintaks yang typo dan menyebabkan error
   3. Menurtu kamu AI apa membantu dalam analysis sebua data?
   == ya, karena AI bisa menganalisis data dengan cepat,menemukan pola tersembunyi,dan membantu membuat grafik atau kesimpulan ototmatis tanpa harus menghitung dengan manual
   ```
