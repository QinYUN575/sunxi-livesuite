obj-m := awusb.o
KDIR := /lib/modules/$(shell uname -r)/build
PWD := $(shell pwd)

default:
	$(MAKE) -C $(KDIR) M=$(PWD) modules
clean:
	$(MAKE) -C $(KDIR) M=$(PWD) clean
	rm -rf Module.markers module.order module.sysvers 
	
install: default
	mkdir -p /lib/modules/$(shell uname -r)/kernel/drivers/usb
	cp -f awusb.ko /lib/modules/$(shell uname -r)/kernel/drivers/usb
	depmod -a
