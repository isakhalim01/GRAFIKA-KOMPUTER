<h1 align=center>📌 PENJELASAN </h1>

## Praktikum Koordinat

### Soal 1

Berikut Kodenya :

    print('===== Soal 1 =====')
    import math
    x1 = int(input('Masukkan x1 : '))
    y1 = int(input('Masukkan y1 : '))
    x2 = int(input('Masukkan x2 : '))
    y2 = int(input('Masukkan y2 : '))
    
    print('======= Hasill =======')
    print(f'Titik Pertama : ({x1:.1f}, {y1:.1f})')
    print(f'Titik Kedua : ({x2:.1f}, {y2:.1f})')
    jarak = math.sqrt((x2-x1)**2+(y2-y1)**2)    
    hasil=jarak
    print(f'Jarak antara dua titik : {hasil}')
    
    # tentukan kuadran
    if x1<0 and y1<0:
        kuadran='Kuadran 1'
    elif x1>0 and y1>0:
        kuadran='Kuadran 2'
    elif x1<0 and y1>0:
        kuadran='Kuadran 3'
    elif x1>0 and y1<0:
        kuadran='Kuadran 4'
    elif x1==0 and y1==0:
        kuadran='Titik pusat (0,0)'
    elif x1<0 == 0:
        kuadran='Berada di Sumbu Y'
    else:
        kuadran='Berada di Sumbu X'
    print(f'Titik pertama berada di: {kuadran}')

Berikut Penjelasan kode diatas :

<p><i>
  Kode tersebut digunakan untuk menghitung jarak antara dua titik dan menentukan posisi kuadran dari titik pertama pada bidang koordinat.
Pertama, program meminta pengguna memasukkan koordinat x1, y1, x2, y2 sebagai angka. Lalu, program menampilkan titik pertama dan kedua dengan format satu angka di belakang koma.
Selanjutnya, program menghitung jarak antara kedua titik menggunakan rumus Euclidean:

<p align=center>
  <img width="312" height="50" alt="image" src="https://github.com/user-attachments/assets/0c68c908-9fe8-4075-9869-1e2701998a71" />
</p>
	​
Setelah jarak dihitung, program menentukan kuadran atau posisi titik pertama berdasarkan nilai x1 dan y1:
<ul>
  <li>
    Kuadran 1: x<0 dan y<0
  </li>
  <li>
    Kuadran 2: x>0 dan y>0
  </li>
  <li>
    Kuadran 3: x<0 dan y>0
  </li>
  <li>
    Kuadran 4: x>0 dan y<0
  </li>
  <li>
    Titik pusat: x=0 dan y=0
  </li>
  <li>
    Jika x=0 atau y=0, titik berada di sumbu X atau sumbu Y
  </li>
</ul>

Akhirnya, program menampilkan jarak antara dua titik dan posisi kuadran dari titik pertama.
Catatan: Kondisi elif x1<0 == 0: sepertinya ada kesalahan logika dan tidak akan berfungsi seperti yang dimaksud. Seharusnya dicek dengan x1 == 0 untuk sumbu Y.
</i></p>

Hasil dari kode diatas :

<p align=center>
  <img width="554" height="259" alt="image" src="https://github.com/user-attachments/assets/648da029-ed10-4a6d-bec7-8cfdf131fe9f" />
</p>

##

### Soal 2

Berikut Kodenya :

    print('===== Soal 2 =====')

    lebar = 10
    tinggi = 5
    for y in range (tinggi):
        for x in range (lebar):
            if x == 3 and y == 2:
                print('X', end='')
            else:
                print('.', end='')
        print()

Berikut Penjelasan kode diatas :

<p><i>
  Kode tersebut digunakan untuk menampilkan pola titik-titik pada layar dengan satu karakter khusus 'X' di posisi tertentu.
Program membuat persegi panjang dengan lebar 10 dan tinggi 5, menggunakan nested loop:

<ul>
  <li>
    Loop luar (for y in range(tinggi)) mengatur baris.
  </li>
  <li>
    Loop dalam (for x in range(lebar)) mengatur kolom di setiap baris.
  </li>
</ul>
Di setiap posisi, program memeriksa: jika x == 3 dan y == 2, maka mencetak 'X'; selain itu, mencetak titik '.'.

Hasil akhirnya adalah pola persegi panjang dengan titik-titik, dan karakter 'X' muncul tepat di kolom ke-4 dan baris ke-3 (indeks mulai dari 0).
</i></p>

Hasil dari kode diatas :

<p align=center>
  <img width="383" height="193" alt="image" src="https://github.com/user-attachments/assets/a74c8096-4b23-4ba4-abd3-d755a15e34d8" />
</p>

___________________________

## Praktikum Gambar

### Soal 1

Berikut Kodenya :

    tinggi = 10
    lebar = 10
    grid = [['.' for _ in range(lebar)] for _ in range(tinggi)]
    
    # Menempatkan X di posisi (4,6)
    # Catatan: koordinat (x,y) dimana x=kolom, y=baris
    x_pos = 4
    y_pos = 6
    
    # Validasi posisi
    if 0 <= x_pos < lebar and 0 <= y_pos < tinggi:
        grid[y_pos][x_pos] = 'X'
        print(f"\nPiksel 'X' ditempatkan pada posisi ({x_pos}, {y_pos})\n")
    else:
        print(f"\nPosisi ({x_pos}, {y_pos}) di luar batas grid!\n")
    
    # Tampilkan grid dengan nomor koordinat
    print("  ", end="")
    for i in range(lebar):
        print(i, end=" ")
    print()
    
    for idx, baris in enumerate(grid):
        print(f"{idx} ", end="")
        print(' '.join(baris))


Berikut Penjelasan kode diatas :

<p><i>
  Kode tersebut digunakan untuk membuat grid 10x10 dan menempatkan satu karakter 'X' di posisi tertentu, sekaligus menampilkan seluruh grid dengan koordinat baris dan kolom.

<ul>
  <li>
    Membuat grid:
    
Grid dibuat sebagai list 2D berisi titik '.' menggunakan list comprehension, dengan tinggi = 10 dan lebar = 10.
  </li>
  <li>
    Menentukan posisi 'X':
    
Variabel x_pos = 4 dan y_pos = 6 menunjukkan kolom dan baris tempat karakter 'X' akan ditempatkan.
  </li>
  <li>
    Validasi posisi:
    
Program mengecek apakah koordinat berada di dalam batas grid. Jika ya, karakter 'X' ditempatkan di posisi tersebut, dan menampilkan pesan konfirmasi. Jika tidak, muncul pesan bahwa posisi berada di luar grid.
  </li>
  <li>
    Menampilkan grid:
    
Grid ditampilkan dengan nomor kolom di atas dan nomor baris di samping, sehingga mudah melihat koordinat setiap titik. Karakter 'X' akan muncul tepat di posisi yang ditentukan, sementara posisi lain tetap '.'.
  </li>
</ul>

Hasil akhirnya adalah representasi visual grid 10x10 dengan koordinat, lengkap dengan 'X' di titik (4,6).
</i></p>

Hasil dari kode diatas :

<p align=center>
  <img width="507" height="338" alt="image" src="https://github.com/user-attachments/assets/19d315b5-995f-40e2-ad1a-92f5ebaefee1" />
</p>

##

### Soal 2

Berikut Kodenya :

    x1,y1 = 0,0
    x2,y2 = 5,3
    n=5
    
    points=[]
    for i in range(n+1):
        x = x1+(x2-x1)*i/n
        y = y1+(y2-y1)*i/n
        points.append((round(x),round(y))) 
        print(f'Titik {i} : ({x:.1f},{y:.1f})') 
    print('-------------------')
    print('Garisnya')
    lebar = x2+1 
    tinggi = y2+1
    for i in range(tinggi):
        for k in range(lebar):           
            if i == 0 and k == 0: #pusat
                print('0', end='')           
            elif (k, i) in points: #titik
                print('.', end='')
            elif i == 0:
                print('-', end='') #x          
            elif k == 0:
                print('|', end='')  #y      
            else:
                print(' ', end='')
        print()
    print('')


Berikut Penjelasan kode diatas :

<p><i>
  Kode tersebut digunakan untuk menampilkan pola titik-titik pada layar dengan satu karakter khusus 'X' di posisi tertentu.
Program membuat persegi panjang dengan lebar 10 dan tinggi 5, menggunakan nested loop:

<ul>
  <li>
    Loop luar (for y in range(tinggi)) mengatur baris.
  </li>
  <li>
    Loop dalam (for x in range(lebar)) mengatur kolom di setiap baris.
  </li>
</ul>
Di setiap posisi, program memeriksa: jika x == 3 dan y == 2, maka mencetak 'X'; selain itu, mencetak titik '.'.

Hasil akhirnya adalah pola persegi panjang dengan titik-titik, dan karakter 'X' muncul tepat di kolom ke-4 dan baris ke-3 (indeks mulai dari 0).
</i></p>

Hasil dari kode diatas :

<p align=center>
  <img width="383" height="193" alt="image" src="https://github.com/user-attachments/assets/a74c8096-4b23-4ba4-abd3-d755a15e34d8" />
</p>
