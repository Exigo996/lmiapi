LogMeIn API
===========

This library provides a structured interface to retrieve the data from your
LogMeIn Central account.

This project is not sponsored by or in any way affiliated with LogMeIn, Inc.
LogMeIn is a registered trademark of LogMeIn, Inc.


Public API v2
-------------

This interface connects to the official public LogMeIn Central REST API.  It
requires credentials obtained from the LogMeIn central web interface at
https://secure.logmein.com/frontend/#/users/psk.

LogMeIn's API v2 documentation can be found at:
https://developer.logmein.com/api/api-reference/

    from lmiapi import LogMeInPublicAPIv2
    
    auth = {'companyId': 123467890, 'psk': 'abcde12345ABCDE12345'}
    lmi = LogMeInPublicAPIv2(auth)
    lmi.authentication()
    print(lmi.list_hosts())

More examples using this API can be found in examples/public_v2.py.


Public API v1
-------------

This interface connects to the official public LogMeIn Central REST API.  It
requires credentials obtained from LogMeIn support.

LogMeIn's API documentation can be found at:
https://secure.logmein.com/welcome/documentation/EN/pdf/LogMeInCentralPublicAPIReference.pdf

    from lmiapi import LogMeInPublicAPIv1
    
    auth = {'companyId': 123467890, 'psk': 'abcde12345ABCDE12345'}
    lmi = LogMeInPublicAPIv1(auth)
    lmi.authentication()
    print(lmi.hosts())

More examples using this API can be found in examples/public_v1.py.


Central API
-----------

This interface mimics the requests made using the LogMeIn Central Web UI to
provide additional information unavailable via the public API.  It relies upon
undocumented URLs and interfaces, and may break at any time if LogMeIn updates
their services.  It requires only your email address and password.

    from lmiapi import LogMeInCentralAPI
    
    lmi = LogMeInCentralAPI(email='logmein@example.com', password='l0gm31n')
    print(lmi.get_all_hosts())

More examples using this API can be found in examples/central.py.
