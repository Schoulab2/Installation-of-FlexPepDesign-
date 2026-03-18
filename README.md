# Installation-of-FlexPepDesign-

## Table of Contents

- [Overview](#overview)
- [1. Download Rosetta](#1-download-rosetta)
- [2. Navigate to download location in WSL](#2-navigate-to-download-location-in-wsl)
- [3. Extract Rosetta archive](#3-extract-rosetta-archive)
- [4. Enter Rosetta directory](#4-enter-rosetta-directory)
- [5. Verify directory structure](#5-verify-directory-structure)
- [6. Search for FlexPepDock executable](#6-search-for-flexpepdock-executable)
- [7. Navigate to compiled binaries](#7-navigate-to-compiled-binaries)
- [8. Confirm FlexPepDock binary is present](#8-confirm-flexpepdock-binary-is-present)
- [9. Test FlexPepDock](#9-test-flexpepdock)
- [10. Add Rosetta to PATH](#10-add-rosetta-to-path-temporary)
- [11. Verify PATH](#11-verify-path)
- [12. Make PATH permanent](#12-make-path-permanent)
- [13. Final verification](#13-final-verification)
- [Notes](#notes)
- [Example run](#example-run)
- [Result](#result)

---

## Overview

- Platform: WSL (Ubuntu)
- Installation method: Precompiled Rosetta binaries (no compilation)
- Installed in Windows Downloads folder
- Added to PATH for global access

---

## 1. Download Rosetta

Go to:

https://www.rosettacommons.org/software/license-and-download

Download:

rosetta_bin_linux_3.14_bundle.tar.bz2

Saved to:

/mnt/c/Users/kensch/Downloads

---

## 2. Navigating to download location in WSL
cd /mnt/c/Users/kensch/Downloads
ls -lh

---

## 3. Extracting Rosetta archive
tar -xvjf rosetta_bin_linux_3.14_bundle.tar.bz2

---

## 4. Enter Rosetta directory
cd rosetta.binary.linux.release-371
cd main

---

## 5. Verifying directory structure
ls

---

## 6. Searching for FlexPepDock executable
find . -type f -name "FlexPepDocking*"

---

## 7. Navigating to compiled binaries
cd source/build/src/release/linux/5.4/64/x86/gcc/4.8/static
ls

---

## 8. Confirming FlexPepDock binary is present
ls | grep FlexPepDocking

Expected:

FlexPepDocking.static.linuxgccrelease

---

## 9. Testing FlexPepDock
./FlexPepDocking.static.linuxgccrelease -help

Exit help:
q

---

## 10. Adding Rosetta to PATH (temporary)
export PATH=/mnt/c/Users/kensch/Downloads/rosetta.binary.linux.release-371/main/source/build/src/release/linux/5.4/64/x86/gcc/4.8/static:$PATH

---

## 11. Verifying PATH
which FlexPepDocking.static.linuxgccrelease

---

## 12. Making PATH permanent
echo 'export PATH=/mnt/c/Users/kensch/Downloads/rosetta.binary.linux.release-371/main/source/build/src/release/linux/5.4/64/x86/gcc/4.8/static:$PATH' >> ~/.bashrc
source ~/.bashrc

---

## 13. Final verification
FlexPepDocking.static.linuxgccrelease -help

---

## Notes

- No compilation required
- No additional dependencies needed
- Works inside WSL
- Independent of conda/mamba environments

---

## Example run
FlexPepDocking.static.linuxgccrelease 
-s complex.pdb 
-database /mnt/c/Users/kensch/Downloads/rosetta.binary.linux.release-371/main/database 
-pep_refine 
-nstruct 50

---

## Result

FlexPepDock / FlexPepDesign is:

- Installed
- Working
- Available globally via PATH
ads/rosetta.binary.linux.release-371/main/database
-pep_refine
-nstruct 50<img width="739" height="2722" alt="image" src="https://github.com/user-attachments/assets/49fb53f7-c822-437a-99f0-4a7351aff933" />
