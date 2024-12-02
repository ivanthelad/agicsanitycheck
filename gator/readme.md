
# How to test the annotations check 
the folder tests holds 3 tests scenarios 
 - [happy path](tests/happypath.yaml). an typical ingress example 
 - [fail-due-to-forbidden-annotations](tests/fail-due-to-forbidden-annotations.yaml)  "This test checks if a use is using the annotation kubernetes.io/ingress.class instead of the class name"
 - [fail-due-to-forbidden-annotations-with-classname](tests/fail-due-to-forbidden-annotations-with-classname.yaml) This test checks if a user is using the class name instead of the legacy annotation ingress.class"
    appgw.ingress.kubernetes.io/waf-policy-for-path: "ishouldnotbesettingthis


## Run the gator test suite
Execute the gator verify command `gator verify`

```bash
└─> gator verify gator/suite.yaml  -v
=== RUN   disallowed-tags
    === RUN   happypath-ingress
    --- PASS: happypath-ingress	(0.005s)
    === RUN   fail-due-to-forbidden-annotations
    --- PASS: fail-due-to-forbidden-annotations	(0.002s)
    === RUN   fail-due-to-forbidden-annotations-with-classname
    --- PASS: fail-due-to-forbidden-annotations-with-classname	(0.003s)
--- PASS: disallowed-tags	(0.017s)
ok	gator/suite.yaml	0.017s
PASS
```