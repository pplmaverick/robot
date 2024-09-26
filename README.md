class AutonomousTaxi:
    def __init__(self, location, destination):
        self.location = location  # 當前位置
        self.destination = destination  # 目的地
        self.passengers = 0  # 初始乘客數量
        self.is_driving = False  # 計程車是否在行駛

    def pick_up_passenger(self, passengers):
        if self.passengers == 0:
            self.passengers = passengers
            print(f"Picked up {passengers} passengers.")
        else:
            print("Taxi is already occupied.")

    def drop_off_passenger(self):
        if self.passengers > 0:
            print(f"Dropped off {self.passengers} passengers at {self.destination}.")
            self.passengers = 0
        else:
            print("No passengers to drop off.")

    def drive(self):
        if self.passengers > 0:
            self.is_driving = True
            print(f"Driving from {self.location} to {self.destination}...")
            # 模擬行駛過程
            self.location = self.destination
            self.is_driving = False
            self.drop_off_passenger()
        else:
            print("No passengers to drive.")

# 創建無人計程車對象並進行操作
taxi = AutonomousTaxi("Downtown", "Airport")
taxi.pick_up_passenger(3)
taxi.drive()
# robot
