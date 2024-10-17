class RoboticArm:
    def __init__(self):
        self.joint_angles = [0, 0, 0]  # 三個關節的角度：底部、肘部、腕部
        self.grip_open = True  # 爪子是否打開

    def move_joint(self, joint, angle):
        if 0 <= joint < len(self.joint_angles):
            self.joint_angles[joint] = angle
            print(f"Joint {joint} moved to {angle} degrees.")
        else:
            print("Invalid joint number.")

    def open_grip(self):
        self.grip_open = True
        print("Grip opened.")

    def close_grip(self):
        self.grip_open = False
        print("Grip closed.")

    def status(self):
        print(f"Joint angles: {self.joint_angles}, Grip open: {self.grip_open}")

# 創建一個 RoboticArm 物件並進行操作
arm = RoboticArm()
arm.move_joint(0, 45)  # 移動底部關節到45度
arm.move_joint(1, 90)  # 移動肘部關節到90度
arm.close_grip()       # 關閉爪子
arm.status()
# RoboticArm
