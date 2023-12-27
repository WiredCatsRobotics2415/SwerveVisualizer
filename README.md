This is a plugin to visualize 4 swerve modules.

Installation:
 - Download the latest release
 - Insert the file into the Shuffleboard/plugins folder in your user directory
 - In robot code, use the following as a template to create the initSendable method

```java
@Override
    public void initSendable(SendableBuilder builder) {
        builder.setSmartDashboardType("SwerveModuleState");
        builder.addDoubleProperty("setSpeed", () -> this.getSetState().speedMetersPerSecond, null);
        builder.addDoubleProperty("setAngle", () -> this.getSetState().angle.getDegrees(), null);
        builder.addDoubleProperty("actualSpeed", () -> this.getState().speedMetersPerSecond, null);
        builder.addDoubleProperty("actualAngle", () -> this.getState().angle.getDegrees(), null);
    }
 ```
  - Note: You will need the SwerveModule class to implement Sendable!
  - Once that is added, all that needs to happen is sending the module with something like SmartDashboard.put("Module 1", modules[0]) periodically
  - They will autopopulate on shuffleboard
  - Make sure to order them logically, ie. Front left module widget is in the front left, etc.
