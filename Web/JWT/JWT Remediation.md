[[JWT]] [[JWT Flaws]]
#jwt/remediation
How to prevent JWT attacks

You can protect your own websites against many of the attacks we've covered by taking the following high-level measures:

    Use an up-to-date library for handling JWTs and make sure your developers fully understand how it works, along with any security implications. Modern libraries make it more difficult for you to inadvertently implement them insecurely, but this isn't foolproof due to the inherent flexibility of the related specifications.

    Make sure that you perform robust signature verification on any JWTs that you receive, and account for edge-cases such as JWTs signed using unexpected algorithms.

    Enforce a strict whitelist of permitted hosts for the jku header.

    Make sure that you're not vulnerable to path traversal or SQL injection via the kid header parameter.

Additional best practice for JWT handling

Although not strictly necessary to avoid introducing vulnerabilities, we recommend adhering to the following best practice when using JWTs in your applications:

    Always set an expiration date for any tokens that you issue.

    Avoid sending tokens in URL parameters where possible.

    Include the aud (audience) claim (or similar) to specify the intended recipient of the token. This prevents it from being used on different websites.

    Enable the issuing server to revoke tokens (on logout, for example).
