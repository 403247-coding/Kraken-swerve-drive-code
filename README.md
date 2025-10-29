# Kraken-swerve-drive-code
//state motor names
//set power to motors
//make motors move
//easy peasy looll not
test\x60 motor

import com.qualcomm.robotcore.eventloop.opmode.LinearOpMode;
import com.qualcomm.robotcore.eventloop.opmode.TeleOp;
import com.qualcomm.robotcore.hardware.TalonSRX;

@TeleOp(name="Basic Motor Spin", group="Tutorial")
public class BasicMotorSpin extends LinearOpMode {

    private TalonSRX test_motor = null;

    @Override
    public void runOpMode() {
        // Initialize the motor
        test_motor = hardwareMap.get(TalonSRX.class, "test_motor");

        // Set motor direction if needed (e.g., if it spins backward initially)
        // test_motor.setDirection(TalonSRX.Direction.REVERSE);

        telemetry.addData("Status", "Initialized");
        telemetry.update();

        waitForStart(); // Wait for the start button to be pressed

        while (opModeIsActive()) {
            // Set motor power to 1 (full speed forward)
            test_motor.setPower(1);

            telemetry.addData("Status", "Running");
            telemetry.update();
        }

        // Stop the motor when the OpMode ends
        test_motor.setPower(0);
        telemetry.addData("Status", "Stopped");
        telemetry.update();
    }
}










