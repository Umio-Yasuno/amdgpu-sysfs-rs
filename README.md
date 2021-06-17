# amdgpu-syfs-rs
[![Crates.io](https://img.shields.io/crates/v/amdgpu-sysfs)](https://crates.io/crates/amdgpu-sysfs)

This library allows you to interact with the Linux Kernel SysFS interface for GPUs (mainly targeted at the AMDGPU driver). 

Basic usage:

```rust
let sysfs_path = PathBuf::from_str("/sys/class/drm/card0/device").unwrap();

let gpu_controller = GpuController::new_from_path(sysfs_path).unwrap();

let gpu_usage = gpu_controller.get_busy_percent().unwrap();

let total_vram = gpu_controller.get_total_vram().unwrap();
```
