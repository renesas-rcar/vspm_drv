CFILES = vspm_main.c vspm_sub.c
CFILES += frame.c
CFILES += manager/vspm_control.c manager/vspm_drv_vsp.c manager/vspm_drv_fdp.c manager/vspm_exec_manager.c
CFILES += manager/vspm_job_manager.c manager/vspm_lib.c manager/vspm_sort_queue.c manager/vspm_task.c
CFILES += vsp/vsp_drv.c vsp/vsp_drv_phy.c vsp/vsp_drv_par.c
CFILES += fdp/fdp_drv.c fdp/fdp_drv_l.c

obj-m += vspm.o
vspm-objs := $(CFILES:.c=.o)

U_INCLUDE := -I$(PWD)
U_INCLUDE += -I$(PWD)/../include
EXTRA_CFLAGS += $(U_INCLUDE)

all:
	make -C $(KERNELSRC) M=$(PWD) modules
clean:
	make -C $(KERNELSRC) M=$(PWD) clean
install:
	$(CP) ../include/vspm_public.h $(KERNELSRC)/include
	$(CP) ../include/vspm_cmn.h $(KERNELSRC)/include
	$(CP) ../include/vsp_drv.h $(KERNELSRC)/include
	$(CP) ../include/fdp_drv.h $(KERNELSRC)/include
	$(CP) ../include/vspm_cmn.h $(INCSHARED)
	$(CP) ../include/vsp_drv.h $(INCSHARED)
	$(CP) ../include/fdp_drv.h $(INCSHARED)

