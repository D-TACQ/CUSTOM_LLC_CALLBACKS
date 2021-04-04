README for package: custom_llc_callbacks

Install callbacks to act on MGT DMA changes

/usr/local/init/custom_llc_callbacks.init

.. starts a daemon that monitors MGT400 (PCIe) DMA start and stop for PUSH and PULL.

daemon has 3 actions
- on_push_up : PUSH DMA START .. start a continuous capture ie ARM the ADC system
- on_push_down : PUSH DMA STOP .. stop the capture
- on pull_down : PULL DMA STOP .. call awg_abort to clear all outputs.

This means that an HOST-SIDE Control Program can completely orchestrate a capture WITHOUT access to Ethernet.

actions are recorded to syslog, so, with rsyslog enabled, a HOST system can verify that everything happened as normal.


