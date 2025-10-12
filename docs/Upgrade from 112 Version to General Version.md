# Upgrade from 112 Version to General Version

## Requirement

| Current Verion (112 version)                  | Target Version (General Version)    |
| --------------------------------------------- | ----------------------------------- |
| X1N0400_M04.1029_B3.5.10_DC25090896_DEBUG_OUT | X1N0400_M04.1029_V3.5.6.9_R24090904 |

## Precondition

- [ ] **Upgrade Public Key**: "F:\config\upgrade.pem"
- [ ] **Transitional version**: "F:\upgrade\X1N0400_M04.1029_B3.5.6_R25010305_RSA"
- [ ] **Target Version**: "F:\upgrade\X1N0400_M04.1029_V3.5.6.9_R24090904"

> [!IMPORTANT]
>
> <kbd>[Click here](https://wj.streamax.com:9443/outpublish.html?code=Bfffdd179ee984b8c84284fd02c324ac5&lang=zh-cn#view)</kbd> to download all the needed files, then copy and paste them to your EasyCheck.

## Steps

### Import the Upgrade Public Key

![Import the Upgrade Public Key](https://cdn.jsdelivr.net/gh/maozuxiao/Image-shack/image-20251010194648290.png)

### Upgrade to the Transitional version

![Upgrade to the Transitional version A](https://cdn.jsdelivr.net/gh/maozuxiao/Image-shack/image-20251010195826489.png)

### Delete the Transitional version from EasyCheck 

> [!IMPORTANT]
>
> Delete **Transitional version**: "F:\upgrade\X1N0400_M04.1029_B3.5.6_R25010305_RSA" from EasyCheck is mandatory!

### Upgrade to the Target Version

![Upgrade to the Target Version](https://cdn.jsdelivr.net/gh/maozuxiao/Image-shack/image-20251010201151079.png)

### Done

![Upgrade Success](https://cdn.jsdelivr.net/gh/maozuxiao/Image-shack/image-20251010201900052.png)