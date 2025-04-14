# CBT079
Converted to GitHub via [cbt2git](https://github.com/wizardofzos/cbt2git)

This is still a work in progress. 
Due to amazing work by Alison Zhang and Jake Choi repos are no longer deleted.

```
//***FILE 079 IS FROM WILLIAM SMITH, FORMERLY OF CHARLES SCHWAB IN  *   FILE 079
//*           SAN FRANCISCO, CALIFORNIA.  THIS FILE CONTAINS A      *   FILE 079
//*           ROBUSTLY IMPLEMENTED "PRODUCTION" ISPF INTERFACE      *   FILE 079
//*           FOR IBM'S DCF SCRIPT/VS.  A PROTOTYPE ADDON IS        *   FILE 079
//*           ALSO INCLUDED, TO CONVERT THIS INTERFACE INTO A       *   FILE 079
//*           CUA COMPLIANT FORMAT.                                 *   FILE 079
//*                                                                 *   FILE 079
//*         ADDRESS:   WILLIAM SMITH                                *   FILE 079
//*                    IBM                                          *   FILE 079
//*                    STORAGE SYSTEMS DIVISION                     *   FILE 079
//*                    5600 COTTLE ROAD                             *   FILE 079
//*                    DEPT. W98A                                   *   FILE 079
//*                    DRIVER BUILD & INTEGRATION                   *   FILE 079
//*                    BUILDING 50, ROOM A382                       *   FILE 079
//*                    SAN JOSE, CA 95193-0001                      *   FILE 079
//*                    (408) 256-1557 OR                            *   FILE 079
//*                    TIE LINE 276-1557                            *   FILE 079
//*                                                                 *   FILE 079
//*         email:     smithwj@us.ibm.com                           *   FILE 079
//*                    sfowjs@sbcglobal.net                         *   FILE 079
//*                                                                 *   FILE 079
//*           THERE ARE OTHER INTERESTING ITEMS IN THIS             *   FILE 079
//*           FILE, WHICH ARE MOSTLY DESCRIBED BELOW:               *   FILE 079
//*                                                                 *   FILE 079
//*    THIS COLLECTION OF TOOLS COMPRISES:                          *   FILE 079
//*                                                                 *   FILE 079
//*    DCF SCRIPT/VS ISPF INTERFACE, AS FOLLOWS:                    *   FILE 079
//*                                                                 *   FILE 079
//*    1)  A COMPLETE PRODUCTION ISPF DIALOG INTERFACE TO           *   FILE 079
//*        IBM'S DCF SCRIPT/VS FACILITY.                            *   FILE 079
//*                                                                 *   FILE 079
//*        TO INSTALL THIS INTERFACE, YOU NEED MEMBERS:             *   FILE 079
//*        PLIB1, MSGS, CLIST1 TO BE IEBUPDTE-LOADED TO             *   FILE 079
//*        A PANEL LIBRARY, A MESSAGE LIBRARY, AND A                *   FILE 079
//*        CLIST LIBRARY, RESPECTIVELY.  ALSO, YOU WILL             *   FILE 079
//*        NEED ASSEMBLED, MEMBER IKJCT44B FROM THE SOURCE          *   FILE 079
//*        MEMBER IN THIS PDS.  THIS SOURCE MUST BE ASSEMBLED,      *   FILE 079
//*        LINKEDITED, AND PLACED IN A (LINKLIST) LIBRARY           *   FILE 079
//*        THAT IS ACCESSIBLE TO YOUR TSO SESSION.                  *   FILE 079
//*                                                                 *   FILE 079
//*        THIS PRODUCTION INTERFACE IS NOT CUA COMPLIANT           *   FILE 079
//*        AS IT IS.                                                *   FILE 079
//*                                                                 *   FILE 079
//*    2)  A PROTOTYPE MODIFICATION TO THE ABOVE DCF SCRIPT/VS      *   FILE 079
//*        INTERFACE, TO MAKE IT CUA COMPLIANT.  THIS CONSISTS      *   FILE 079
//*        OF PANELS AND CLISTS TO SUBSTITUTE FOR LIKE-NAMED        *   FILE 079
//*        MEMBERS IN THE PANEL AND CLIST LIBRARIES CREATED         *   FILE 079
//*        BY THE ABOVE INSTALLATION.                               *   FILE 079
//*                                                                 *   FILE 079
//*        PART OF THIS PROTOTYPE ADDITION CONSISTS OF AN           *   FILE 079
//*        ISPF PRIMARY OPTION MENU CONTAINING A CALENDAR           *   FILE 079
//*        AND ACTION BAR PULL-DOWNS.                               *   FILE 079
//*                                                                 *   FILE 079
//*        TO INSTALL THIS INTERFACE, YOU NEED MEMBERS:             *   FILE 079
//*        PLIB2, CLIST2 TO BE IEBUPDTE-LOADED INTO PANEL           *   FILE 079
//*        AND CLIST LIBRARIES THAT WILL BE CONCATENATED AHEAD      *   FILE 079
//*        OF THE RESPECTIVE LIBRARIES CREATED BY THE INSTALL       *   FILE 079
//*        PROCESS IN ITEM 1) ABOVE.                                *   FILE 079
//*                                                                 *   FILE 079
//*    IN ADDITION TO THE DCF SCRIPT/VS ISPF INTERFACE, THIS        *   FILE 079
//*    FILE CONTAINS THE FOLLOWING OTHER MEMBERS:                   *   FILE 079
//*                                                                 *   FILE 079
//*     SOURCE    -  A COLLECTION OF VARIOUS EXITS TO JES2          *   FILE 079
//*                  RELATING TO TSO.  THERE IS ALSO A TSO          *   FILE 079
//*                  SESSION MANAGER EXIT, AND A GDDM PLOTTER       *   FILE 079
//*                  EXIT.  THIS MEMBER IS IN IEBUPDTE UNLOADED     *   FILE 079
//*                  FORMAT AND MUST BE IEBUPDTE-LOADED INTO A      *   FILE 079
//*                  PARTITIONED DATASET.                           *   FILE 079
//*                                                                 *   FILE 079
//*                  INCLUDED IN THIS MEMBER IS A CLIST VARIABLE    *   FILE 079
//*                  EXTENSION EXIT (IKJCT44B) THAT IS REQUIRED     *   FILE 079
//*                  BY MEMBER PLIB1.  THIS MEMBER ADDS SOME        *   FILE 079
//*                  BUILT-IN FUNCTIONS TO THE CLIST LANGUAGE       *   FILE 079
//*                  AND IS REQUIRED FOR THE DCF SCRIPT/VS          *   FILE 079
//*                  INTERFACE.                                     *   FILE 079
//*                                                                 *   FILE 079
//*     USERMODS  -  A COLLECTION OF ASSORTED MVS AND JES2          *   FILE 079
//*                  LOCAL MODS PACKAGED IN SMP FORMAT.  THE        *   FILE 079
//*                  USEFULNESS OF THIS COLLECTION LIES IN          *   FILE 079
//*                  THE FACT THAT THEY ARE SAMPLE MODS TO          *   FILE 079
//*                  IBM PRODUCTS, WHICH IBM NEVER PROVIDED         *   FILE 079
//*                  SAMPLES FOR.                                   *   FILE 079
//*                                                                 *   FILE 079
//*     DOCLIB    -  THIS IS A 30-PAGE DOCUMENT DESCRIBING          *   FILE 079
//*                  THE DCF SCRIPT/VS DIALOG FRONTEND, AND         *   FILE 079
//*                  ITS HISTORY.  THIS WAS A PRESENTATION          *   FILE 079
//*                  GIVEN AT SHARE 80 IN SAN FRANCISCO.            *   FILE 079
//*                                                                 *   FILE 079
//*     DEFMACRO  -  A COLLECTION OF SCRIPT MACROS FOR VIRTUALLY    *   FILE 079
//*                  EVERY FONT FAMILY MARKETED BY IBM.  THIS       *   FILE 079
//*                  COLLECTION ALLOWS EASY USE OF MANY FONTS       *   FILE 079
//*                  BY A SCRIPT USER.                              *   FILE 079
//*                                                                 *   FILE 079
//*     PUBTOOLS  -  THE COMPLETE CHARLES SCHWAB IN-HOUSE           *   FILE 079
//*                  STANDARDS GUIDE FOR MAINFRAME-BASED DESKTOP    *   FILE 079
//*                  PUBLISHING, IN SCRIPT FORMAT.  (THIS TAKES     *   FILE 079
//*                  TIME TO FORMAT AND PRINT ON AN IBM PRINTER--   *   FILE 079
//*                  ABOUT 40 MINUTES ON A 3820.)                   *   FILE 079
//*                                                                 *   FILE 079
```
