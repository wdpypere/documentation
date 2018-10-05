
### DESCRIPTION

The _sudo_ component manages the sudo configuracion, I.E: edits
`/etc/sudoers`. It doesn't provide as strict and nice syntax and
semantic correction as visudo(8) does, but it tries to warn on most
common users' mistakes.

### EXAMPLES

Try the following settings:
  prefix "/software/components/sudo";
  "general\_options/options" = dict("insults", true);
  "user\_aliases/FOO" = list("127.0.0.1");
  "privilege\_lines" = list(dict(
      "user", "foo",
      "run\_as", "ALL",
      "host", "ALL",
      "cmd", "ALL"
      ));

and see the resulting `/etc/sudoers`.

### WARNINGS

This component cannot perform such as exhaustive analysis as visudo
does. Be careful with what you specify on your profiles or you will
break sudo!!
