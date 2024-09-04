- ## SDK-Related File Downloads

- Download Link: [https://mega.nz/folder/uVZW0AQA#LRBYIT-3ZgAqTz407XXicw](https://mega.nz/folder/uVZW0AQA#LRBYIT-3ZgAqTz407XXicw)

- ## Start Compiling

1. Create a new folder, such as `cm68sdk`.
   ```
   mkdir cm68sdk
   cd cm68sdk
   ```
2. Copy the downloaded files into this directory and use the `md5sum -c` command to verify the files. If the verification fails, please re-download the corrupted archive files. ![](https://raw.githubusercontent.com/zzcatvs/CM68_SDK/main/img/1.png)

3. Extract the SDK using the command:
   ```
   tar -xvJf Cm68_SDK_2024-09-04.tar.xz
   ```

4. Release the source code using the command:
   ```
   git reset --hard
   ```


5. Extract the buildroot `dl` files and drivers.

   ```
   tar -xvJf cm68_buildrrot_dl_2024-09-04.tar.xz
   ```


6. For the first build, compile buildroot first by running `./build.sh` and selecting the first option `cm68-buildroot_defconfig`.

   ```
   ./build.sh
   ```

   ![](https://raw.githubusercontent.com/zzcatvs/CM68_SDK/main/img/2.png)

7. After compiling, you should see the result as shown below: ![](https://raw.githubusercontent.com/zzcatvs/CM68_SDK/main/img/3.png)

8. Upon successful compilation, image files will be generated in the `rockdev/` directory. For a full package flash, use the image with the date suffix: `updatexxx.img`. ![](https://raw.githubusercontent.com/zzcatvs/CM68_SDK/main/img/4.png)

9. Compile uboot separately.

   ```
   ./build.sh uboot
   ```
- [x] 
  Generated image path: `u-boot/`


- [x] Generated images: `uboot.img`, `trust.img`, etc.


10. Compile the kernel separately.

     ```
     ./build.sh kernel
     ```

- [ ]  Generated image path: `rockdev/`


- [ ]  Generated image: `boot.img`


11. Compile buildroot separately.

     ```
     ./build.sh buildroot
     ```

- [ ]  Generated image path: `rockdev/`


- [ ]  Generated image: `rootfs.img`


12. Compile recovery separately.

     ```
     ./build.sh recovery
     ```

13. Compile the Debian system.

 1. After downloading the SDK and compiling buildroot once, extract the Debian filesystem archive to the SDK's Debian directory.

    ```
    tar -xvJf linaro-rootfs.img.tar.xz; mv linaro-rootfs.img debian/
    ```

 2. Run the command `./build.sh init` and select the second option `cm68-debian_defconfig` to switch the system. ![](https://raw.githubusercontent.com/zzcatvs/CM68_SDK/main/img/5.png)

 3. Compile the Debian system globally.

    ```
    ./build.sh
    ```

- ## System Information

    ```
    Username: linaro
    Password: linaro
    If you are not very familiar with linux, do not use the root user to log in. Misoperation may cause damage to the system.
    Username: root
    Password: root
    ```

