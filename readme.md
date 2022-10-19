<h1 align="center">
  <a href="https://github.com/ankitwasankar/mftool-java">
    <img src="https://raw.githubusercontent.com/ankitwasankar/mftool-java/master/src/main/resources/icons/mf-tool-java-new.jpg" alt="mftool-java">
  </a>
</h1>
<p align="center">
<a href="https://search.maven.org/artifact/com.webencyclop.core/mftool-java"><img src="https://img.shields.io/maven-central/v/com.webencyclop.core/mftool-java.svg?label=Maven%20Central"/></a> 
<a href="https://travis-ci.com/github/ankitwasankar/mftool-java"><img src="https://travis-ci.com/ankitwasankar/mftool-java.svg?branch=master" /></a>
<a href="https://github.com/ankitwasankar/mftool-java/blob/master/license.md"><img src="https://camo.githubusercontent.com/80a1153c429992993a5fc1d8009c2f9ed74f95263366dc21a2daec8fb25077c9/68747470733a2f2f696d672e736869656c64732e696f2f62616467652f646570656e64656e636965732d7570253230746f253230646174652d627269676874677265656e2e737667" /></a>
<a href="https://www.linkedin.com/in/ankitwasankar/"><img height="20" src="https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white" /></a>
</p>
<p align="center">
  This repository contains the <strong>MF TOOL - JAVA</strong> source code.
  MF TOOL - JAVA is a java library developed to ease the process of working with Indian Mutual Funds. It's a powerful, actively maintained and easy to use java library.
</p>
<hr/>

# Introduction
mftool-java is a library for getting Mutual Funds data in India in Java applications. 
It can be used in various types of projects which requires getting live quotes for a given scheme.

###### Note: This library requires internet connection to fetch Mutual Fund data.

# Features
- Fetch list of all the mutual fund schemes with their scheme-codes.
- Match keyword with names of mutual fund list. (useful in auto-suggestion in searches).
- Fetch historic NAV for the fund.
- Fetch current NAV.
- Fetch NAV for specific date.
- Fetch Fund Details for fund.
- Returns data in Java Objects.

# Documentation
###### Add dependency from Maven Central https://search.maven.org/artifact/com.webencyclop.core/mftool-java

##### Maven
```
<dependency>
  <groupId>com.webencyclop.core</groupId>
  <artifactId>mftool-java</artifactId>
  <version>1.0.4</version>
</dependency>
```
##### Graddle
```
implementation 'com.webencyclop.core:mftool-java:1.0.4'
```

#### How to use in Java code:
```
// Return the List of mutual funds which matches keyword "Axis"
MFTool mfTool = new MFTool();
List<SchemeNameCodePair> list = mfTool.matchingScheme("Axis");

// Retuns List of all the mutual fund list in India
MFTool tool = new MFTool();
List<SchemeNameCodePair> list = tool.allSchemes();

// Retuns the Mutual Fund details - Axis fund: 120503
MFTool tool = new MFTool();
SchemeDetails details = tool.schemeDetails("120503");

// Returns hisoric NAV data - Axis fund: 120503
MFTool tool = new MFTool();
List<Data> list = tool.historicNavForScheme("120503");

// Returns current NAV for mutual fund
MFTool tool = new MFTool();
BigDecimal nav = tool.getCurrentNav("120503");

// Returns NAV for specific date
MFTool tool = new MFTool();
BigDecimal nav = tool.getNavFor("120503", LocalDate.parse("2021-07-13"));
```

