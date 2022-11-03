---
title: Unspecific Commands
_build:
  list: false
---

## AT+EGMR (Modem Revision)

- Test Command: `AT+EGMR=?`

  Response:

  ```at
  +EGMR: (0,1),(5,7,9,10)

  OK
  ```

- Execution Command: `AT+EGMR=<mode>,<format>,<data>`

  Response: `OK` or `ERROR`

Parameter:

```csv
Name,Value,Note
\<mode>,0,Read
,1,Write
,2,Read
\<format>,5,[Unknown]
,7,SIM 1 slot IMEI
,9,[Unknown]
,10,SIM 2 slot IMEI
```

Example:

```at
AT+GSN
+GSN: "111111111111111"

OK
AT+EGMR=1,7,"000000000000000"
OK
AT+GSN
+GSN: "000000000000000"

OK
```

see <https://github.com/the-modem-distro/pinephone_modem_sdk/issues/39>

see <https://docs.ai-thinker.com/_media/b_and_t/nb-iot/n92/kaifazhidaowendang/rda8908a_at_commandmanual9.0.pdf>

## AT+ADBON (Enable ADB)

see <https://github.com/the-modem-distro/meta-qcom/blob/1f5dc4a6/recipes-modem/openqti/files/src/atfwd.c#L155-L164>

- Execution Command: `AT+ADBON`

  Response: `OK` or `ERROR`

## AT+ADBOFF (Disable ADB)

see <https://github.com/the-modem-distro/meta-qcom/blob/1f5dc4a6/recipes-modem/openqti/files/src/atfwd.c#L155-L164>

- Execution Command: `AT+ADBOFF`

  Response: `OK` or `ERROR`