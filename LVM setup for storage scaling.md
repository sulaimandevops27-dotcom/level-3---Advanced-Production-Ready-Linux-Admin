# ✅ Task 3: LVM Setup for Storage Scaling

This guide explains how to **use LVM (Logical Volume Manager)** to manage disk space dynamically.  
LVM allows you to **create, resize, and manage storage volumes** without downtime.

---

## ✅ Step 1: Check Available Disks

**Explanation:**  
Identify which disks are available for LVM.

```bash
lsblk
```

---

## ✅ Step 2: Create a Physical Volume (PV)

**Explanation:**  
A Physical Volume is a disk or partition that LVM will manage.

```bash
sudo pvcreate /dev/sdb
```

---

## ✅ Step 3: Create a Volume Group (VG)

**Explanation:**  
A Volume Group combines one or more PVs into a **single storage pool**.

```bash
sudo vgcreate myvg /dev/sdb
```

---

## ✅ Step 4: Create a Logical Volume (LV)

**Explanation:**  
A Logical Volume acts like a **virtual partition** that you can format and mount.

```bash
sudo lvcreate -L 10G -n mylv myvg
```

---

## ✅ Step 5: Format and Mount the Logical Volume

**Explanation:**  
Format the LV with a filesystem and mount it for use.

```bash
sudo mkfs.ext4 /dev/myvg/mylv
sudo mkdir /mnt/data
sudo mount /dev/myvg/mylv /mnt/data
```

---

## ✅ Step 6: Optional – Make Mount Permanent

**Explanation:**  
Add the LV to `/etc/fstab` to mount automatically at boot.

```bash
sudo nano /etc/fstab
```

Add the line:

```
/dev/myvg/mylv  /mnt/data  ext4  defaults  0  2
```

---

## 🎉 LVM Setup Complete!

You can now **dynamically manage storage**, resize volumes, and scale your system easily.
