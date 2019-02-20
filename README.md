T32 for Linux Debugging
=======================
# Setup
1. setup ITSP
   http://www.trace32.com/customer/itsp.php?mnu=5
1. setup example
    http://trace32.com/wiki/index.php/TRACE32_Update
1. Build Image


# T32  
1. LINUX는 Kernel Image를 올려서 Debugging을 한다.
1. T32는 ELF Format에서 Symbol정보가 있으면 편리하다.
1. Application은 Start_addr 기반으로 offset값으로 추적한다.
1. T32는 Kernel에서 현재 실행하는 Task 정보를 parsing한다.
1. hypervisor는 경우에 따라 parsing이 불가능할 수 있다.
1. T32는 Linux 이외에도 다양한 OS를 지원하고 있다.
1. JTAG 연결시 Attach는 현재상테에서 올리는 것, UP은 Target을 리셋시킨 후 올린다.
# T32 Kernel Debugging
1. data.dump Command 는 일반적으로 Virtual Adress를 dump한다
1. Physical Address를 dump하려면 data.dump a:address 로 써야한다.
1. Kernel은 build시 path를 기반으로 build 되므로 windows에서 load 시 PowerView를 읽어올 수 없으므로 반드시 Source PATH를 지정해줘야한다. PATH지정 시 PATH가 대체된다.
1. mmu.list.pt(kpt) 를 통하여 Current Memory Table(Kernel)을 볼 수 있다.
1. mmu.list.tpt "Task Name" 을 통하여 TASK에 대한 Table을 볼 수 있다.
1. SMP AMP 셋팅가능하다.
1. Kernel의 자원을 볼 수 있도록 만들어져있다.(Awareness)

