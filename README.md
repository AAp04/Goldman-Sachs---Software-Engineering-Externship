# Goldman Sachs Software Engineering Externship

As part of my responsibilities as a governance analyst, I have conducted a thorough assessment of our organization's password security measures. Below are my findings based on the password dump provided and the associated cracking techniques:

Hashing Algorithm:

The passwords were hashed using MD5 (32-bit) encryption. This algorithm, while widely used in the past, is susceptible to fast cracking techniques due to its lack of salting and vulnerability to precomputed rainbow tables.
Level of Protection:

The MD5 hashing algorithm provides a basic level of protection but is no longer considered secure. Given the advances in password cracking tools, it is crucial to adopt more robust algorithms such as SHA-256 or bcrypt for enhanced security.
Controls to Enhance Security:

Implement Password Salting: To mitigate the risk of rainbow table attacks, I recommend implementing password salting. This involves appending a unique random string (salt) to each password before hashing, significantly enhancing the complexity of the password hash.
Password Policy Assessment:

The organization's password policy appears weak, as evidenced by the prevalence of easily guessable passwords in the dump. There is a need for improvement in password length, complexity, and key space.
Proposed Changes to Password Policy:

Increase Password Length: Enforce a minimum password length of at least 12 characters to enhance complexity and resist brute-force attacks.
Require Special Characters: Mandate the inclusion of special characters in passwords to thwart common dictionary attacks.
Regularly Update Passwords: Encourage users to update their passwords periodically to minimize the impact of a potential breach.
In conclusion, our current password security measures, primarily relying on MD5, pose a significant risk to the organization. Implementing the suggested controls, such as adopting stronger hashing algorithms, introducing password salting, and enforcing a more robust password policy, will fortify our defenses against malicious actors.


## Here is a sample file of accounts:
```
experthead:e10adc3949ba59abbe56e057f20f883e
interestec:25f9e794323b453885f5181f1b624d0b
ortspoon:d8578edf8458ce06fbc5bb76a58c5ca4
reallychel:5f4dcc3b5aa765d61d8327deb882cf99
simmson56:96e79218965eb72c92a549dd5a330112
bookma:25d55ad283aa400af464c76d713c07ad
popularkiya7:e99a18c428cb38d5f260853678922e03
eatingcake1994:fcea920f7412b5da7be0cf42b8c93759
heroanhart:7c6a180b36896a0a8c02787eeafb0e4c
edi_tesla89:6c569aabbf7775ef8fc570e228c16b98
liveltekah:3f230640b78d7e71ac5514e57935eb69
blikimore:917eb5e9d6d6bca820922a0c6f7cc28b
johnwick007:f6a0cb102c62879d397b12b62c092c06
flamesbria2001:9b3b269ad0a208090309f091b3aba9db
oranolio:16ced47d3fc931483e24933665cded6d
spuffyffet:1f5c5683982d7c3814d4d9e6d749b21e
moodie:8d763385e0476ae208f21bc63956f748
nabox:defebde7b6ab6f24d5824682a16c3ae4
bandalls:bdda5f03128bcbdfa78d8934529048cf
```
## Cracked passwords:
```
experthead: 123456
ortspoon: qwerty
reallychel: password
simmson56:  111111
bookma:12345678
popularkiya7: abc123
eatingcake1994: 1234567
heroanhart: password1
edi_tesla89: password!
liveltekah: qazxsw
blikimore: Pa$$word1
johnwick007: bluered
flamesbria2001: Flamesbria2001
oranolio: Oranolio1994
spuffyffet: Spuffyffet12
moodie: moodie00
nabox: nAbox!1
bandalls: Banda11s
```
## Analysis:

After the conducted analysis it was determined that organization uses an outdated password hashing algorithm (MD5) which offers very little protection in the event of a password database leaking. It was also determined that the current password policy is not aligned with industry best practices allowing users to have short passwords (6 characters) and reuse usernames as part of passwords. 

As a result of the analysis the following uplifts are proposed to increase the overall level of password protection: 

- Use a dedicated password hashing algorithm bcrypt, scrypt or PBKDF2 as this will greatly increase the time needed to crack individual passwords,
- Implement salting to prevent usage of rainbow tables to speed up cracking,
- Increase the minimum password length requirement to 10 characters – this will increase the computational effort required to crack password and will give additional time to change all passwords in the event of the password database being leaked,
- Prevent passwords to be the same as usernames or reused as part of the password – such password combination is easy to check without gaining access to the password database itself. 
- It is advised to educate users on creating safe and easy to remember passwords. Having a password policy requiring long passwords with a number of special characters results in user writing passwords down or constantly resetting them. The best way to create a strong and user-friendly password is using passphrases (e.g.  mygrannyschairhadstaples). The best way to create such passwords is to combine a couple of completely random word. It’s also advised to use some special characters and numbers as easy to remember substitutions to expand the key space (e.g. mYgranny$cha1rhadstaples)
- Educate users on the benefits of passwords managers. Having a password manager allows having very long and completely random passwords (e.g. M>?{tk6Cfep6BrZ4J)KZWQ8j) without the need to remember/write down. A strong passphrase is still required as a master key for to access the password manager.
