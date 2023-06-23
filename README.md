# ER-D

![image](https://github.com/verz666/basis_data_praktikum_6/assets/115523263/2d91fc84-0997-40bb-8b6e-1f3f6ab0e0be)

## table perusahaan 

![image](https://github.com/verz666/basis_data_praktikum_6/assets/115523263/267e2212-e4f7-4dc1-b69b-1e27ac6c672f)

## table departement

![image](https://github.com/verz666/basis_data_praktikum_6/assets/115523263/963dd1fe-c9d2-44cc-b08d-fafcf23bd2dc)

## table karyawan

![image](https://github.com/verz666/basis_data_praktikum_6/assets/115523263/48fa828e-9fa7-41a9-b8cf-9790d383787c)

## table project

![image](https://github.com/verz666/basis_data_praktikum_6/assets/115523263/46ce2a4c-1067-428c-a21e-28a2b9fa3211)

## table project_detail

![image](https://github.com/verz666/basis_data_praktikum_6/assets/115523263/e21b941a-03b3-4006-a142-e3229558ed6b)

-------------

# Latihan

- Tampilkan data karyawan yang bekerja pada departemen yang sama dengan karyawan yang bernama Dika

      SELECT *
      FROM employee
      WHERE id_dept = (
      SELECT id_dept
      FROM employee
      WHERE nama = 'Dika'
      );

    ![image](https://github.com/verz666/basis_data_praktikum_6/assets/115523263/811303ca-3e57-4121-b26d-32e4ed252b91)

- Tampilkan data karyawan yang gajinya lebih besar dari rata-rata gaji semua karyawan. urutkan menurun berdasarkan besaran gaji

      SELECT *
      FROM employee
      WHERE gaji_pokok > (
      SELECT AVG(gaji_pokok)
      FROM employee
      )
      ORDER BY gaji_pokok DESC;

    ![image](https://github.com/verz666/basis_data_praktikum_6/assets/115523263/1c715b57-2e7b-4c5d-987b-e9c77e9dd87d)

- Tampilkan nik dan nama karyawan untuk semua karyawan yang bekerja di department yang sama dengan karyawan dengan nama yang mengandung huruf 'K'.

      SELECT nik, nama
      FROM employee
      WHERE id_dept IN (
      SELECT id_dept
      FROM employee
      WHERE nama LIKE '%K%'
      );

    ![image](https://github.com/verz666/basis_data_praktikum_6/assets/115523263/0c0da4be-5066-4529-8654-105758fc32cb)

- Tampilkan data karyawan yang bekerja pada departemen yang ada di kantor pusat.

      SELECT *
      FROM employee
      WHERE id_dept IN (
      SELECT id_dept
      FROM department
      WHERE id_p = 'P01'
      );

    ![image](https://github.com/verz666/basis_data_praktikum_6/assets/115523263/02bd5207-a8b2-43b7-a295-c0620533cdf6)

- Tampilkan nik dan nama karyawan untuk semua karyawan yang bekerja di department yang sama dengan karyawan dengan nama yang mengandung huruf 'K' dan yang gajinya lebih besar dari rata-rata gaji semua karyawan

      SELECT nik, nama
      FROM employee
      WHERE id_dept IN (
      SELECT id_dept
      FROM employee
      WHERE nama LIKE '%K%'
      )
      AND gaji_pokok > (
      SELECT AVG(gaji_pokok)
      FROM employee
      );

    ![image](https://github.com/verz666/basis_data_praktikum_6/assets/115523263/00dc3aea-9881-4c17-af31-70d1e40c3e18)
