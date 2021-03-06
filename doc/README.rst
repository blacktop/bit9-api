.. image:: https://raw.githubusercontent.com/blacktop/bit9-api/master/doc/logo.png

bit9-api
========

.. image:: https://travis-ci.org/blacktop/bit9-api.svg?branch=master
    :target: https://travis-ci.org/blacktop/bit9-api

.. image:: https://badge.fury.io/py/bit9-api.png
    :target: http://badge.fury.io/py/bit9-api

.. image:: https://pypip.in/d/bit9-api/badge.png
        :target: https://crate.io/bit9-api/requests/

.. image:: http://img.shields.io/gittip/blacktop.svg
        :target: https://www.gittip.com/blacktop/

Bit9 API for their Cyber Forensics Service

https://www.bit9.com/solutions/cloud-services/cyber-forensics

Installation
------------

.. code-block:: bash

    $ pip install bit9-api


Usage
-----
.. code-block:: python

    import json
    from bit9_api import Bit9Api

    USER = 'user'
    PASSWORD = 'password'

    bit9 = Bit9Api(USER, PASSWORD)

    # Win 7 SP1 - calc.exe
    calc_exe_md5 = '60B7C0FEAD45F2066E5B805A91F4F0FC'

    response =  bit9.lookup_hashinfo(calc_exe_md5)
    print json.dumps(response, sort_keys=False, indent=4)


Output:
-------
.. code-block:: json

    {
        "hashinfo": {
            "peheadermetadata": {
                "fileversion": "6.1.7601.17514 (win7sp1_rtm.101119-1850)",
                "language": "English (United States)",
                "companyname": "Microsoft Corporation",
                "codepage": "Unicode",
                "productname": "Microsoft\u00ae Windows\u00ae Operating System",
                "version": "6.1.7601.17514",
                "productversion": "6.1.7601.17514",
                "originalname": "CALC.EXE",
                "description": "Windows Calculator"
            },
            "fileinfo": {
                "firstseendateutc": "2011-02-10T20:24:00Z",
                "ispeformat": true,
                "iscontainer": true,
                "firstseenname": "calc.exe",
                "sha256": "80c10ee5f21f92f89cbc293a59d2fd4c01c7958aacad15642558db700943fa22",
                "sha1": "9018a7d6cdbe859a430e8794e73381f77c840be0",
                "crc32": "-1919983730",
                "ssdeep": "6144:Jv7Wc4dyC7dXNBzn68YoC+6VoQSkgrpZHqk61peBN1L+I8pfezYeWHMzyy14pL1k:JvSbJxPRC+XQSxb6Dc7RwIWHeGL7GOK                                     ",
                "filesizebytes": "776192",
                "isexecutable": true,
                "md5": "60b7c0fead45f2066e5b805a91f4f0fc"
            },
            "trust": "10",
            "threat": "0",
            "certificate": {
                "commonname": "Microsoft Windows                                                                                                               "
            }
        },
        "request": "/1/hashinfo/lookup.json?md5=60b7c0fead45f2066e5b805a91f4f0fc&flags=15&tool=pythonapi&data="
    }


Testing
-------

To run the tests:

    $ ./tests

Documentation
-------------

Documentation is comming soon.

Contributing
------------

1. Fork it.
2. Create a branch (`git checkout -b my_bit9_api`)
3. Commit your changes (`git commit -am "Added Something Cool"`)
4. Push to the branch (`git push origin my_bit9_api`)
5. Open a [Pull Request](https://github.com/blacktop/bit9-api/pulls)
6. Wait for me to figure out what the heck a pull request is...
