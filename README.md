# Pa300 一键移调（手机网页遥控）

安卓 Chrome 打开页面，OTG 线连 KORG Pa300 背后 USB TO HOST，点数字直接跳到该移调。

原理：发送 MIDI 标准 Universal Real Time SysEx「Master Coarse Tune」`F0 7F 7F 04 04 00 (40+半音) F7`。
Pa300 OS 2.1.1 固件（OPOS）在 GMCmds 模块里注册了这条指令，收到后换算成主移调（Master Transpose，限 -11..+11）。
伴奏遥控按 Pa300 手册印刷页 378：Control 通道 Program Change 80–94 / 103。
