ros tracked robot
Ros giữa kỳ: mô phỏng xe bánh xích với tay máy 2 khớp revolute, cùng với 3 cảm biến lidar imu encoder
Hướng dẫn chạy giả lập:
- Bước 1: Khi tải file về hãy vào view_robot_pkg/urdf/robot_description để cập nhật đường dẫn ros2 control cho file controllers
- Bước 2: Chuẩn bị 4 terminal được dẫn tới folder view_robot_pkg
- Bước 3:
    + Ở terminal 1: sau build pkg và chạy install, nhập lệnh ros2 launch view_robot_pkg gazebo.launch.py để chạy giả lập
    + Ở terminal 2: sau khi install, nhập lệnh ros2 run teleop_twist_keyboard teleop_twist_keyboard để điều khiển xe
    + Ở terminal 3: sau khi install, nhập lệnh ros2 run view_robot_pkg orange_dashboard để chạy node show giá trị imu và encoder
    + Ở terminal 4: sau khi install, nhập lần lượt các lệnh:
      . ros2 control load_controller --set-state active joint_state_broadcaster
      . ros2 control load_controller --set-state active arm_controller
      Để có thể kích hoạt các controller cho tay máy
      . chạy lệnh điều khiển tay máy: ros2 run view_robot_pkg arm_teleop
      
