# analisis-nilai-siswa

## Langkah-langkah Analisis

1. **Import Library**
   ```python
   import pandas as pd
   import matplotlib.pyplot as plt
   import seaborn as sb

2. **Membaca File CSV**
   ```python
   data = pd.read_csv('nilai_siswa.csv')
   data.info()
   data.head()
   data.describe()

3 **Menampilkan Statistik Dasar**
   ```python
   print("Rata-rata:", data['Nilai'].mean())
   print("Median:", data['Nilai'].median())
   print("Modus:", data['Nilai'].mode()[0])

4. **Memisahkan Data Per Mapel**
   ```python
   matematika = data[data['Matpel'] == 'Matematika']
   produktif = data[data['Matpel'] == 'Produktif']
   inggris = data[data['Matpel'] == 'Bahasa Inggris']
   indo = data[data['Matpel'] == 'Bahasa Indonesia']
   fisika = data[data['Matpel'] == 'Fisika']

5. **Mengelompokan Data & Menghitung Rata-Rata**
   ```python
   rata = data.groupby('Matpel')['Nilai'].mean()
   print(rata)

6. **Mebuat Grafik Batang**
   ```python
   rata.plot(kind='bar')
   plt.title('Rata-rata Nilai per Mapel')
   plt.xlabel('Mata Pelajaran')
   plt.ylabel('Nilai Rata-rata')
   plt.show()

7. **Membuat Boxplot**
   sb.boxplot(x='Matpel', y='Nilai', data=data)
  plt.title('Sebaran Nilai per Mata Pelajaran')
  plt.show()
   
