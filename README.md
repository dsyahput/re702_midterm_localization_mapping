# RE702 Midterm Localization & Mapping

Repositori ini dibuat sebagai bagian dari pengerjaan asesmen tengah semester mata kuliah Lokalisasi dan Pemetaan (RE702).
Package ROS2 ini bertujuan untuk menggerakkan TurtleBot4 dari satu posisi ke posisi lain serta mengaktifkan buzzer, sesuai instruksi asesmen.

## Persiapan Sebelum Menjalankan Package

Sebelum melakukan build dan menjalankan package ROS2 ini, pastikan Anda telah menghasilkan peta map sesuai dengan environment yang digunakan.   
Peta hasil mapping disimpan pada folder `maps/`. Untuk membuat peta baru, Dapat mengikuti dokumentasi TurtleBot4:  
https://turtlebot.github.io/turtlebot4-user-manual/tutorials/generate_map.html  
Pastikan perangkat (laptop/PC) telah terhubung ke LAN atau WiFi yang sama dengan TurtleBot4, kemudian lakukan SSH ke robot.


## Menjalankan Lokalisasi & Navigasi

Di terminal TurtleBot4, jalankan:
```sh
ros2 launch turtlebot4_navigation localization.launch.py map:=path/ke/map.yaml
```
> Pastikan `path/ke/map.yaml` diganti dengan path file map yang benar.

Di terminal TurtleBot4 lainnya, jalankan:
```sh
ros2 launch turtlebot4_navigation nav2.launch.py
```

Pada terminal laptop/PC yang terhubung dengan TurtleBot4, jalankan:
```sh
ros2 launch turtlebot4_viz view_navigation.launch.py
```
> Sesuaikan posisi (pose) robot di RViz2 agar sesuai dengan posisi sebenarnya pada map.

## Build Package dari Repository Ini

Buat workspace:
```sh
mkdir ros2_ws/src
cd ros2_ws/src
```

Clone repository:
```sh
git clone https://github.com/dsyahput/re702_midterm_localization_mapping.git
```

Build workspace:
```sh
cd ..
colcon build
source install/setup.bash
```

Jalankan program:
```sh
ros2 run re702_midterm_localization_mapping navigation
```

## Demo
Demontrasi penggunaan package dapat dilihat pada link berikut:
https://youtu.be/xT1oOv827p0?si=qy-sIwNF8kH5rmCL
