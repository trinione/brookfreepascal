## INTRODUCTION

**Brook framework** is the perfect [Free Pascal](http://freepascal.org/) framework for your web applications. It's pure Pascal. You don't need to leave your preferred programming language.

It's complete: simple actions or configurable actions for database access, advanced routing features, wizard for [Lazarus](http://lazarus.freepascal.org), support for internationalization, high compatibility with [JSON](http://json.org) structures, easy and elegant [REST](http://en.wikipedia.org/wiki/Representational_state_transfer) implementation, plugins for varied needs, extensible and decoupled brokers... In fact, you have several reasons to adopt Brook as your web development framework.

## FEATURES

* **Advanced routes management** – Actions are performed by means of routes. Brook knows how to receive a request and choose the correct URL and the correct method to reply to it.
* **Integrated data persistance** – Brook offers a table object where data can be handled. Less instantiations, less coding, with an elegant syntax.
* **JSON native support** – [JSON](http://json.org) is widespred in the web for data exchange purposes. You will really appreciate Brooks' good JSON support.
* **REST architecture support** – [REST](http://en.wikipedia.org/wiki/Representational_state_transfer) is an architecture able to simplify and standardize data requests and replies. Brook is powerful even if you don't use REST – but you will want to use it.
* **Lazarus wizards for installation and usage** - With [Lazarus](http://www.lazarus.freepascal.org), development is easier; with the Brook wizards, only a few clicks are required to start and configure your Brook projects.

## GET STARTED

#### If you use Free Pascal only:

Create three files:

* `cgi1.lpr`;
* `unit1.pas`;
* `brokers.pas`;

In `cgi1.lpr`, type:

```pascal
program cgi1;
 
{$mode objfpc}{$H+}
 
uses
  BrookApplication, Brokers, Unit1;
 
begin
  BrookApp.Run;
end.
```

In `unit1.pas`, type:

```pascal
unit Unit1;
 
{$mode objfpc}{$H+}
 
interface
 
uses
  BrookAction;
 
type
  TMyAction = class(TBrookAction)
  public
    procedure Get; override;
  end;
 
implementation
 
procedure TMyAction.Get;
begin
  Write('Hello world!');
end;
 
initialization
  TMyAction.Register('*');
 
end.
```

In `brokers.pas`, type:

```pascal
unit Brokers;

{$mode objfpc}{$H+}

interface

uses
  BrookFCLCGIBroker;

implementation

end. 
```

Compile the project `cgi1.lpr` and copy the resulting file to CGI directory of your web server. Now, in your web browser, access the following URL:

```
http://localhost/cgi-bin/cgi1
```

***

#### If you are a Lazarus user:

Open and install the file `brookex.lpk`. After the installation, select _File | New ..._ and, in _Brook framework_, choose the _Simple CGI application_ option as shown in the figure below:

![Brook - New project](https://raw.githubusercontent.com/silvioprog/brookframework/gh-pages/images/brook_new-project.png)

Save and compile the project. Copy the resulting file to the CGI directory of your web server and enjoy! See the final result:

![Brook - Hello world](https://raw.githubusercontent.com/silvioprog/brookframework/gh-pages/images/brook_hello-world.png)

## PLUGINS

* **[dOPF](https://github.com/risoflora/brookfreepascal/tree/master/plugins/dopf)** – This plugin is sleek, intuitive and fast object persistence for faster and easier database development.
* **[RUtils](https://github.com/risoflora/brookfreepascal/tree/master/plugins/rutils)** – This plugin offers some general purpose routines on string conversions, parsings, encodings and others.
* **[JTemplate](https://github.com/risoflora/brookfreepascal/tree/master/plugins/jtemplate)** – This plugin helps you to fill variables in a template file.
* **[QTemplate](https://github.com/leledumbo/QTemplate)** – This plugin implements an alternative to FPTemplate engine.
* **[EasyRSS](https://github.com/silvioprog/easyrss)** – This plugin is the easiest way of Pascal developers provide news updating services in their applications.
* **[XMailer](https://github.com/risoflora/brookfreepascal/tree/master/plugins/xmailer)** – This plugin offers a really simple way to send e-mails using Free Pascal..
* **[AlgEx](https://github.com/risoflora/brookfreepascal/tree/master/plugins/algex)** – This plugin helps you to process algebric expressions passed as string.
* **[MGeoIP](https://github.com/risoflora/brookfreepascal/tree/master/plugins/mgeoip)** – This plugin allows you to identify the name of country or city which IPs come from.
* **[ConvUtils](https://github.com/risoflora/brookfreepascal/tree/master/plugins/convutils)** – This plugin allows you to convert one measure (centimeters, inches, liters etc.) to another.
* **[HtmlDoc](https://github.com/risoflora/brookfreepascal/tree/master/plugins/htmldoc)** – Whith this plugin you can write headers, body and other relevant tags using Object Pascal.
* **[LJGridUtils](https://github.com/risoflora/brookfreepascal/tree/master/plugins/ljgridutils)** – This plugin offers easy conversion from LCL to JSON and vice versa.

## LICENSE

The source code of the Brook framework is distributed under the GNU Lesser General Public License. See the [project licence](https://github.com/risoflora/brookfreepascal/blob/master/LICENSE.txt) for copyright/license details.

## SYSTEM REQUIREMENTS

Free Pascal **3.0.4** and Lazarus **1.8.4**.

## DOCUMENTATION

The project documentation is available in two formats: [HTML](http://silvioprog.github.io/brookframework/doc/index.html) and [PDF](http://silvioprog.github.io/brookframework/doc/brookframework-ref.pdf).

## VERSIONING

For transparency and insight into our release cycle, and for striving to maintain backward compatibility, Brook framework will be maintained under the Semantic Versioning guidelines as much as possible.

Releases will be numbered with the following format:

`<major>.<minor>.<release>`

And constructed with the following guidelines:

* Breaking backward compatibility bumps the major (and resets the minor and release);
* New additions without breaking backward compatibility bumps the minor (and resets the release);
* Bug fixes and misc changes bumps the release;

For more information on SemVer, please visit [http://semver.org](http://semver.org).

## SUPPORT, BUGS, CONTACT

Please use the [issues page](https://github.com/risoflora/brookfreepascal/issues). Your cooperation will be appreciated.

## CONTRIBUTORS

Brook would not be possible without important and active contributors. See their names [here](https://github.com/risoflora/brookfreepascal/blob/master/CONTRIBUTORS.txt).

<a href="https://www.paypal.com/cgi-bin/webscr?cmd=_donations&business=GE9VT768TLP74&lc=GB&item_name=Brook%20framework&item_number=brookframework&currency_code=USD&bn=PP%2dDonationsBF%3abtn_donateCC_LG%2egif%3aNonHosted">
  <img src="https://www.paypalobjects.com/en_US/GB/i/btn/btn_donateCC_LG.gif">
</a>

See the name of all donors [here](https://github.com/risoflora/brookfreepascal/blob/master/DONORS.txt).

## DOWNLOAD

You can download the last release [here](https://github.com/risoflora/brookfreepascal/releases). Alternatively, you can also follow the project's GIT repository. The address is:

`https://github.com/risoflora/brookfreepascal.git`

## THIRD PARTY

The Brook supports third party solutions and, for these, there is a broker file implementing your features. You can download the package containing all files [here](http://silvioprog.github.io/brookframework/download/third-party.zip).

## Welcome to world of Brook! ![Welcome to the Brook's world!](http://l.yimg.com/us.yimg.com/i/mesg/emoticons7/113.gif)
