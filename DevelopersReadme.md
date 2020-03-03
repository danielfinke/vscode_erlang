# Developer's Readme

## Build

At the very first time install some packages in project directory:
(make sure [Node.js](https://nodejs.org) is installed on your machine)

    cd /path/to/vscode_erlang
    npm install
    npm install -g vsce

Build the extension and create a VSIX package for manual distributing:

    ./rebar3 compile
    vsce package

## Test

At _"Run and Debug"_ choose _"Launch Extension"_.

## Language syntax file

According VSCode Extension API:
> As a grammar grows more complex, it can become difficult to understand and
> maintain it as json. If you find yourself writing complex regular expressions
> or needing to add comments to explain aspects of the grammar, consider using
> yaml to define your grammar instead.
>
> Yaml grammars have the exact same structure as a json based grammar but allow
> you to use yaml's more concise syntax, along with features such as multi-line
> strings and comments.

To work easier with TextMate YAML language files install VSCode extension
[TextMate Languages](https://marketplace.visualstudio.com/items?itemName=Togusa09.tmlanguage)
from _Ben Hockley_.

Convert between TexMate PLIST (Property List) XML and YAML formats:

* Use commands _"Convert to YAML-tmLanguage file"_ and
  _"Convert to tmLanguage file"_ provided by extension _TextMate Languages_.

* Alternatively download
  [plist-yaml-plist](https://github.com/grahampugh/plist-yaml-plist)
  from Github and use below command: (On Windows use WSL)

      cd syntaxes
      /path/to/plist_yaml.py erlang.tmLanguage erlang.tmLanguage.yaml
      # Edit YAML file here ... then if you are ready convert back to PLIST
      /path/to/yaml_plist.py erlang.tmLanguage.yaml erlang.tmLanguage

## References

1. Visual Studio Code [Extension API](https://code.visualstudio.com/api)
