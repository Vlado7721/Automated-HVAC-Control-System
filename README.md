# Automated-HVAC-Control-System
Transitioning from large-scale general electrical installations to advanced industrial automation, this project represents a complete retrofit of a manually operated HVAC system. The objective was to eliminate human error, optimize energy consumption, and ensure strict hardware safety by migrating the control logic to a Schneider Electric Modicon TM221 PLC using EcoStruxure Machine Expert - Basic.

The system autonomously manages a Daikin Chiller and an Industrial Boiler, utilizing a strictly organized software architecture divided into dedicated Program Organization Units (POUs) for Inputs, Manual/Auto Modes, and Output processing.

Core Engineering Features & Logic Implementation:

Robust State Machine & Architecture: Developed clean, modular ladder logic by separating signal acquisition (INPUT), state processing (MAN_PROGRAM), and final execution (POU_Modes).

Analog Signal Processing (4-20mA): Implemented precise scaling for external temperature sensors (PT100/TSOP), converting raw analog inputs into engineering units for real-time process monitoring.

Mission-Critical Interlocks: Designed complex hardware and software interlocking mechanisms. The logic processes dry contact feedback from valve actuators, ensuring heavy loads (Chiller/Boiler) cannot start unless the water circuit is in the exact required position, preventing catastrophic mechanical failures.

Power-On Delay & Auto-Recovery: Engineered a specialized recovery sequence for power outages. By utilizing system bits (%S1 Warm Start) combined with TON timers, the PLC holds the system in a safe state, allowing grid voltage to stabilize before automatically and sequentially restarting heavy consumers.

Operator Safety & Edge Detection: Replaced static manual switches with momentary push buttons managed by One-Shot (Rising Edge / |P|) logic. This anti-restart protection guarantees that a jammed physical button will not force the system into an unsafe continuous run state.

Conclusion
This retrofit bridges the gap between traditional power distribution and modern, intelligent control systems. It provides a highly reliable, autonomous environment that protects expensive HVAC assets while offering seamless operational control.

Tech Stack: Schneider Electric Modicon TM221, EcoStruxure Machine Expert - Basic, Ladder Logic, HVAC Automation, Process Control.
