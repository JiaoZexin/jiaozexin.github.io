---
layout: post
title:  "Perl Tutorial"
date:   2023-11-20 13:55:00 +0000
categories: bioinformatics update
---

# Perl Tutorial

Normally, `Perl` is an inner tool in Centos


## Module Install
 
There are so many modules for `Perl`. We need to know how to install modules for `Perl`.

Use module `SVG` as an example.

1st, install cpan
For Debian/Ubuntu:
```
bashCopy code
sudo apt-get install cpanminus
```
For Red Hat/CentOS:
```
bashCopy code
sudo yum install perl-App-cpanminus
```
2nd, install `SVG`

Type `cpan` and then type `install SVG`


Note: For **"LDBlockshow error, Can't locate SVG.pm"**, install SVG with root.

## Debug

Search Perl module path
```
perl -e 'print join "\n",@INC;'
```

### yum安装

1、首先，利用yum search进行搜索，例如
```
yum search Config::General
```
2、找到对应的模块，使用安装即可。
```
yum install -y perl-Config-General.noarch
```
### cpanm安装

但是并不是所有的perl模块都在yum的软件源里，很多依然无法使用yum来安装。以前有cpan工具来安装，不过现在又有了更加好用的cpanm工具来管理perl的模块。

1、首先安装cpanm工具
```
yum search cpanm
yum install -y perl-App-cpanminus.noarch
```
2、利用cpanm进行安装，由于cpanm默认将模块安装到每个用户的家目录下，这样如果使用root来安装，安装到/root目录下其他用户无法使用，因此，需要单独指定安装目录。
```
cpanm --help
cpanm  --mirror https://mirrors.163.com/cpan --prompt  -l /usr/share/perl5  Carp Clone Config::General Cwd SVG Data::Dumper  Digest::MD5 File::Basename  File::Spec::Functions  File::Temp Font::TTF::Font GD GD::Image Getopt::Long IO::File List::MoreUtils List::Util Math::VecStat Memoize Math::Bezier Set::IntSpan Params::Validate Pod::Usage POSIX Readonly Regexp::Common Storable Sys::Hostname Text::Balanced Text::Format Time::HiRes IO::String IO::Scalar YAML PerlIO parent XML::Parser FindBin Math::Round Getopt::Long XML::NamespaceSupport XML::SAX::Base XML::SAX XML::Quote XML::Simple PerlIO::gzip URI::Escape Mail::Send Date::Format
```
如果安装完依然找不到模块，因为cpanm会在创建bin，lib，man三个目录，lib有包含一个perl5目录，这就需要将路径添加到PERL5LIB变量中。
```
export PERL5LIB=/usr/share/perl5/lib/perl5:$PERL5LIB 
```
一步到位

如果你为了省事，那么可以运行以下代码，一步到位。
```
yum search perl-  #搜索所有软件源里的perl模块
yum install -y perl-*  #安装所有软件源里的perl模块
```

### Enviroment check

```
perl -V
perl -e 'print "@INC";'
perl -e 'print join("\n", @INC);'
perldoc -l SVG
```

