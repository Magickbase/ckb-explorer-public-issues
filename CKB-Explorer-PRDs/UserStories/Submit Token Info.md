## About
Currently, the browser provides a method for developers to upload Token Info via email to the developer community. However, this method is no longer sufficient to meet the needs of new frameworks like Kuai for SUDT development. Instead, an API for Token Info uploading should be introduced as a replacement.


For API part, it’s sure that: 
1. It will be open for all UDT project.
2. Uploading info function has a limit from tech side to ensure the service work normally.
3. Uploading info needs admin to approve.


So a workflow are also supposed be added to ensure the TokenInfo can only be modified to the Token creator. Here’s the flow chart to avoid some attacks like update the decimal to make transfer amount 10x than it's, so the attacker can cheat others by claiming that he/she has sent 10x sudt.


Notes: Because the Author Emails was not required in elder Token Info, these token’s Author Email should be set as CKB Explorer’s  official email address.

## Token Info Submit First time

![1](Submit%20Token%20Info_img/1.png)  


### Entrances

A Token Info author could submit Token Info from:
- the Submit Token Info link on CKB explorer Token List page, 
  - Like [XUDT List page](../Pages/TokenListPages/XUDT_List.md);
- The Submit Token Info link on CKB explorer footer, see [footer](../GeneralComponents/Footer.md);

### Pop-up
![2](Submit%20Token%20Info_img/2.png)  


## Token Info Modify

### Entrances
A Token Info author could submit Token Info from Modify Token Info button on the Specific Token Info Page.

![3](Submit%20Token%20Info_img/3.png)  

### Pop up
![4](Submit%20Token%20Info_img/4.png)  

#### Code Email Template

Dear Token Info Author,

To ensure the effectiveness of your Token Info modification operation, we have generated a verification code for you to complete the Token Info update.

Your verification code is: [XXXXXX]

Please note that this verification code is only valid for the next 10 minutes. Please use it to complete your Token Info modification within this time frame and refrain from sharing your code with others. If you have not initiated any action or if this operation is not associated with you, please disregard this email.

If you have any questions or require assistance, please feel free to contact our customer support team.Thank you for your trust and support!

Best regards,
The MagicKBase Team