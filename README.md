
BPOCUnitXMLReporter
===================

BPOCUnitXMLReporter is a small piece of utility code that can be built into an
OCUnit test bundle.  When the tests are run, BPOCUnitXMLReporter will create
an XML test output file in the style of the Ant Java XML plugin.  This allows
OCUnit test results to be processed by various automated build and testing
tools, such as [Hudson][].

Setup
=====
BPOCUnitXMLReporter automatically listens for OCUnit events, so all you have to do to use it is include it in your OCUnit test bundle target.
For portability with iOS, OCUnitXMLReporter depends on GDataXMLNode APIs, which requires you to add the following build settings to your OCUnit test bundle target:
    OTHER_LDFLAGS=-lxml2
    HEADER_SEARCH_PATHS=/usr/include/libxml2
And, of course, add the following 3 files to your project:
    BPOCUnitXMLReporter.m
    GDataXMLNode.h
    GDataXMLNode.m
Finally, you can customize where the xml output goes by setting the `BPOCUnitXMLReporterOut` environment variable to the full path of the xml file you want to write.  Otherwise, it writes `ocunit.xml` to the default directory for your project.

[Hudson]: http://hudson-ci.org/