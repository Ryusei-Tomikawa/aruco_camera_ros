
## aruco_rosについて

aruco_rosの中にlaunchがあるが、そこにはrealsenseとusbカメラを用いたアルコマーカー認識をできるlaunchがある

１．第一にキャリブレーションは各々しておく必要がある
２．認識するマーカーサイズは重要なので、マーカーサイズを測り、適宜launchファイルの"marker_size"の部分を変更すること
３．マーカーサイズに関して、もし難しければ以下のノードを起動することでアルコマーカーを作成することができる

  ```shell
    $ rosrun ar_track_alvar createMarker -s 5.0 -p
  ```
  上記はサイズ5cmを指定しているが、実際には6.1cmくらいになるので,今回使用している"marker_size"には6.1が使用されている
  また、Enterを数回連打していればどんどんマーカーが作成できるため、キリがいいところで"-1"を入力すれば、ホームに.pngのマーカーが作成できる

## realsense_ar_track.launch
 ```shell
    $ roslaunch aruco_ros realsense_ar_track.launch
 ```
 
 Realsenseに関しては、realsense-viewerをできることを前提としています
 
 ## uvc_track.launch
 ```shell
    $ roslaunch aruco_ros uvc_track.launch
 ```
 
 uvc_cameraに関しては、パッケージをaptで入れておけば動くはず
 
 
