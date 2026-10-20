# Wireshark Lab Notes

## Question 1:

For Question 1, made a directory named Question1 as below:

![Screenshot or photo](images/image_01.png)

Get the following file:

```bash
wget https://github.com/SCH-IT-MurdochUni/NetworkingLabs/raw/refs/heads/main/Reusable_Learning_Objects/.test/.misc/lab_red.pcap.enc
```

![Screenshot or photo](images/image_02.png)

Check the file: (file lab_red.pcap.enc will be generated)

![Screenshot or photo](images/image_03.png)

You can decrypt it by adapting the following command for your purposes:

```bash
sudo openssl enc -d -aes-256-cbc -in lab_red.pcap.enc -out lab_red.pcap.enc.tar.bz2 -k ‘2aT9134fnBwC$’
```

The encrypted file gets decrypted as below:

![Screenshot or photo](images/image_04.png)

What percentage of the frames are 802.11 beacons? Answer to 1 decimal place but do not include a % sign

Open the wireshark as: sudo wireshark lab_red.pcap.enc.tar.bz2

![Screenshot or photo](images/image_05.png)

Filter it with ‘wlan.fc.type_subtype == 8’

![Screenshot or photo](images/image_06.png)

**Answer: You can see the result value at the bottom: 31.0 % and so is the answer.**

What is the SSID used?

**Answer: WirelessWPAtest**

![Screenshot or photo](images/image_07.png)

How many frames have been reported as a retransmission? Enter a number:

**Answer: 50**

![Screenshot or photo](images/image_08.png)

## Question 2:

Made Question2 directory:

And get the encrypted file as below:

```bash
wget https://github.com/SCH-IT-MurdochUni/NetworkingLabs/raw/refs/heads/main/Reusable_Learning_Objects/.test/.misc/pp.tar.bz2.enc
```

and file pp.tar.bz2.enc will be downloaded as below:

![Screenshot or photo](images/image_09.png)

Decrypt the file:

```bash
Sudo openssl enc -d -aes-256-cbc -in pp.tar.bz2.enc -out pp.tar.bz2.enc.tar.bz2 -k ‘1&&jbjo7B2za’
```

![Screenshot or photo](images/image_10.png)

Post decryption, you will need to untar the file as below: ‘tar -xvf pp.tar.bz2.enc.tar.bz2’ and two more files will be generated:

![Screenshot or photo](images/image_11.png)

Now open wireshark:

Go to Edit  Preference  Protocols  TLS  and select the sslkeylog.log file as below:

![Screenshot or photo](images/image_12.png)

Click ok

Recover all of the HTTP objects. The second-largest file has three words in it. Write these three words below all lower case with no spaces

Go to File  Export Objects  HTTP  ( Then sort by size ) and select the 2nd largest file and save it.

![Screenshot or photo](images/image_13.png)

In ubuntu, open the saved image from deskop and you will see the image with three words that is drive your dream.

![Screenshot or photo](images/image_14.png)

What frame number is this image requested in? Usually, in wireshark, the frame number is the left-most column. Requests from webpages are often HTTP Gets

Need to work on this: 13588

![Screenshot or photo](images/image_15.png)

## Question 3:

Get the file:

![Screenshot or photo](images/image_16.png)

Decrypt the file:

```bash
Sudo openssl enc -d -aes-256-cbc -in eggtopia_anon_practice.pcap.bz2.enc -out eggtopia_anon_practice.pcap.bz2.enc.tar.bz2 -k ‘Psz#6j^3BqQl’
```

![Screenshot or photo](images/image_17.png)

Open the file in Wireshark. If the data is encrypted, can you find the decryption key? You should use the password list here:

```bash
wget https://raw.githubusercontent.com/SCH-IT-MurdochUni/NetworkingLabs/refs/heads/main/Reusable_Learning_Objects/.test/.misc/leaked_password_list_clean.txt
```

A file named leaked_password_list_clean.txt will be generated as below:

![Screenshot or photo](images/image_18.png)

If you open the leaked_password_list_clean.txt, you can see the list of words, and now from these word you need to decrypt a password:

Cat leaked_password_list_clean.txt

![Screenshot or photo](images/image_19.png)

To get the decryption key, you will need to install aircrack-ng

I have aircrack-ng already installed:

![Screenshot or photo](images/image_20.png)

To decrypt use the below command:
bunzip2 -k eggtopia_anon_practice.pcap.bz2.enc.tar.bz2
aircrack-ng -w leaked_password_list_clean.txt eggtopia_anon_practice.pcap.bz2.enc.tar

![Screenshot or photo](images/image_21.png)

![Screenshot or photo](images/image_22.png)

![Screenshot or photo](images/image_23.png)

## Question 4:

![Screenshot or photo](images/image_24.png)

![Screenshot or photo](images/image_25.png)

```bash
Sudo wireshark 2987.pcap.enc.tar.bz2
```

In wireshark filter it with UDP  right click in UDP under Protocol field  Follow  UDP Stream

![Screenshot or photo](images/image_26.png)

![Screenshot or photo](images/image_27.png)

Enter the contents of the flag. Enter as a string of ascii chars only, no spaces or newlines.

**Answer: 10gQAZ%qgXX5**

What is the source port in use to send this message:

![Screenshot or photo](images/image_28.png)

**Ans: port is 51822**

There is a consistent time delay between messages, from the perspective of the packet capture, what is the delay between each of these messages:

![Screenshot or photo](images/image_29.png)

**Answer: 20**

We can see hat the time difference between the each record is 20 and hence answer is 20
