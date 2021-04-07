# Timeclock Plus Readme

## Contacts

- Anthony Lozano (AL) <ALozano@tcpsoftware.com>

## FAQ

### Cap Rules

**Q. Do we need these cap rules? I'm concerned about annual carryover limits, but aren't those already set in the accrual rules themselves? Otherwise, for caps we would need just as many categories as we have accrual rules, right? Did JMRL create those cap rules, or was that something TCP did in setup?**

**A.** [[AL]](https://mail.google.com/mail/u/0/#inbox/FMfcgxwLtQNpmCgjbqPQHlxnhWBKkVzg) We only need the cap rules if you company does not allow the employee to earn past a certain threshold. The accrual rules themselves are only calculating how many hours the employee should be getting and does not say what each limit is. The limit can be added to the bank itself but if the limit changes with the rule then that’s when the cap rules come into play. There would need to be a cap rule created for each time the limit changes which is usually side by side with the accrual rule.

The cap rules would have been created by JMRL, by default TCP does not have any Cap Rules created.

#### Setting Cap Rules

**Cap rules can affect the accrual forecasts**

**Q. For the "no new accruals" when trying to forecast in the Hours-Individual Hours-Accruals tab it is all banks which aren't forecasting.**

**A.** I found the issue. An accrual Cap has been created and set to “Cease accruing hours if hours exceed” 0.0000. This setting can be found under Configuration> Accruals> Accrual Cap Rules and select the rule. Rule 100, 200 and 300 are all set like this. Examples below.

![image](https://user-images.githubusercontent.com/39073287/113896875-56156d00-9798-11eb-8ab0-897fece1ac3e.png)
