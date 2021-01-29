# Linux check GPU

## PCI Devices

```text
lspci -vnn | grep "VGA\|3D" -A 10
```

## Nvidia

```text
nvidia-smi
```

