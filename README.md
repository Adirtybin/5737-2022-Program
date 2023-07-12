# 5737-2022-Program  
## 20230711 update
## autonomousPeriodic-自动前进与自动旋转更改
```java
// 自动前进
public void go_straight(double meters,double enc){
    drive_left_1.set(auto_drivestraight(-enc, -meters));
    drive_right_2.set(auto_drivestraight(-enc, -meters));
}

public double auto_drivestraight(double current_encoder,double target_meter){
    double auto_straight_out = 0;
    double askp = 0.02;
    auto_straight_out = ((target_meter*21.65)+current_encoder)*askp;
    return auto_straight_out;
}
```
## shuffleboard-功能添加

```java
//创建新表格
ShuffleboardTab NewTab = Shuffleboard.getTab("NewTab");
private NetworkTableEntry GyroYaw = NewTab.add("GyroYaw",0).getEntry();
//更新表格 需要在不断调用的情况下进行更新
public void robotPeriodic() {
    GyroYaw.setDouble(gyro.getYaw());
}

```
