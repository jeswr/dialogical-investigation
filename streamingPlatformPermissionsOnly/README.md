

Here we are also side stepping the fact that age is a temporal variable.

The things we want to demo here:
 - Trust resolution
 - Evaluating consent

Since the movie rating comes from a public webpage; we semantically model that as having a *public read*

# Note that ODRL already has a notion of things like being obliged to pay 
 - We need to justify that that obligation significantly differs from our backwards chaining approach
 to the payments example for the streaming platform.

https://github.com/Dexagod/N3-surfaces-packaging

# ACP (https://www.w3.org/ns/solid/acp)

# A sample ACR c

```
<#card>
    a acp:AccessControlResource;
    acp:resource <./card>;
    acp:accessControl <#publicReadAccess>.

<#publicReadAccess>
    a acp:AccessControl;
    acp:apply [
        a acp:Policy;
        acp:allow acl:Read;
        acp:anyOf [
            a acp:Matcher;
            acp:agent acp:PublicAgent
        ]
    ].
```

General comment:
 - Every policy like acp tries to be the centre of the universe; in particular we *can* make use of the `acp:Policy` but the matchers don't make as much sense when data is already packaged for us.


