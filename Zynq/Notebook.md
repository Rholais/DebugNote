Notebook for Zynq
=================

2013.11.25
----------
* Q: Use `apt-get`
	* A: `deb ftp://ubuntu.csie.nctu.edu.tw/ubuntu/ubuntu trusty main`	

2013.11.24
----------
* Q: Making `reference_nic` `driver_ctrl.c:7:31: fatal error: netlink/genl/genl.h: No such file or directory`
	* A: `apt-get install libnl-dev libpopt-dev` 

2013.10.20
----------
Install VMware Tool.
	
	./vmware-tools-distrib/vmware-install.pl
	.//usr/bin/vmware-user
	
* Q: Unidentified field in ovf 2.0 file.
	* A: Derive to ovf 1.0 file.

2013.10.19
----------
* Q: Can't move VirtualBox VM to Workstation VM.
	* A: Workstation 10.0 only support *.ova | *.ovf | *.vmc | *.vmtm | *.vmx file.

* Q: Windows 8.1 broke down as CRITICAL_STRUCTURE_CORRUPTION error.
	* A: There are conflicts between Windows 8.1 and Oracle VM VirtualBox. 

2013.10.18
----------
* Q: Ubuntu 13.10 Upgrade process was interrupted after it installed `libgc1c2`.
	* A: Forced the system shutdown and recovered it.

2013.10.17
----------
`ps7_gpio_0` was found in device-tree source file made by Xilinx SDK 2013.2.

	ps7_gpio_0: ps7-gpio@e000a000 {
		#gpio-cells = <2>;
		compatible = "xlnx,ps7-gpio-1.00.a";
		emio-gpio-width = <64>;
		gpio-controller ;
		gpio-mask-high = <0x3c000>;
		gpio-mask-low = <0x0>;
		interrupt-parent = <&ps7_scugic_0>;
		interrupts = < 0 20 4 >;
		reg = < 0xe000a000 0x1000 >;
	} ;

This was used to build the block of `ad9516_3` in device-tree source file.

	ad9516_3 {
		compatible = "xjtu,ad9516-gpio";
		/* SPI-GPIOs */
		spi-bus-num = <2>;
		spi-speed-hz = <4000000>;
		spi-mosi-gpio = <&ps7_gpio_0 46 0>;
		spi-miso-gpio = <&ps7_gpio_0 47 0>;
		spi-clk-gpio = <&ps7_gpio_0 48 0>;
		spi-cs-gpio = <&ps7_gpio_0 49 0>;
	};
