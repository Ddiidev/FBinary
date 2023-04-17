
# Fbinary

Fbinary É uma forma de abrir um arquivo binário em um linguagem que não dá suporte a trabalhar com bytes.

Eu fiz só porque queria saber se conseguia fazer isso funcionar e bem, funcionou... Gambiarra das braba.

_Hoje não utilizo o kixtart pra mais nada, mas foi importante pra mim por um tempo, e estou subindo todos os códigos que tenho._

## Uso/Exemplos

```kixtart
include "KiXWithClass.udf"
include "AlsArray.udf"
$include_teste = IncludeClass("fbin", "FileBin.udf")
$fbin = NewClass($include_teste)

$bin = $fbin.ReadBin($path)
```

Escrevendo no arquivo.

```kixtart
include "KiXWithClass.udf"
include "AlsArray.udf"
$include_teste = IncludeClass("fbin", "FileBin.udf")
$fbin = NewClass($include_teste)

$bytes = StringToByteArray("Olá, mundo")
$fbin.WriteBin($path, $bytes)
; OR $fbin.WriteBin_append($path, $bytes)
```

O exemplo a seguir é possível encontrar na pasta examples.
```kixtart
break on
include "KiXWithClass.udf"
include "AlsArray.udf"
$include_teste = IncludeClass("fbin", "FileBin.udf")
$fbin = NewClass($include_teste)
$path = "@curdir\favicon.ico"
$path_o = "@curdir\favicon_teste.ico"

if (exist($path_o))
	del $path_o
endif

$bin = $fbin.ReadBin($path)

$bin = array_merge($bin, StringToByteArray("ola"))

$fbin.WriteBin($path_o, $bin)

get$
```

[![HvOKqKv.png](https://iili.io/HvOKqKv.png)](https://freeimage.host/br)

_Neste exemplo foi aberto o arquivo **favicon.ico** e foi adicionado o texto ola no final do arquivo e salvo em outro arquivo chamado de **favicon_teste.ico**, veja que no final do arquivo está lá o texto e o ícone continua funcionando normalmente._
## Stack utilizada

**Lang:** KiXtart

**Libs(Todas autorais):** AlsArray, FileBin, KiXWithClass

