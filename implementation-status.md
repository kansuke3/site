# コンパイラの実装状況
このページでは、C++のバージョンごとの言語機能を、どのコンパイラがどのバージョンからサポートしているかをまとめる。

ライブラリ機能については、本サイトのリファレンスで各機能を参照してもらいたい。

- [C++11](#cpp11)
- [C++14](#cpp14)
- [C++17](#cpp17)
- [C++20](#cpp20)
- [C++23](#cpp23)

## <a id="cpp11" href="#cpp11">C++11言語機能の実装状況</a>

| 言語機能                         | 説明 | [GCC][gcc] | [Clang][clang] | [ICC][icc] | [MSVC][msvc] |
|----------------------------------|------|-----|-------|-----|------|
| [`alignas`](/lang/cpp11/alignas.md) | アライメント指定 | 4.8 | 3.0 | No | 2015<br/>2003あるいはそれ以前からある`__declspec(align(x))`構文で代替可能。 |
| [`alignof`](/lang/cpp11/alignof.md) | アライメント取得 | 4.5 | 3.3 | No | 2015<br/>2003あるいはそれ以前よりある`__alignof`で代替可能。 |
| [`auto`](/lang/cpp11/auto.md) | 型推論 | 4.4 | 2.9 | 12.0 | 2010 |
| [`decltype`](/lang/cpp11/decltype.md) | 式の型を取得 | 4.3 | 2.9 | 13.0 | 2010 (partial)<br/> 2012 |
| C99互換のプリプロセッサ          | [可変引数マクロ](/lang/cpp11/variadic_macros.md)、[Pragma演算子](/lang/cpp11/pragma_operator.md)、[`__func__`](/lang/cpp11/func.md) | 4.3 | 2.9 | 11.1 | 2005 (partial): 可変引数のみ `_Pragma`の代わりに`__pragma`が存在する。<br/> 2019 Update 6 |
| [`constexpr`](/lang/cpp11/constexpr.md) | 定数式 | 4.6 | 3.1 | 13.0 (partial)<br/> 14.0 | 2015 (partial)<br/> 2015 Update 1 |
| [関数の`default/delete`宣言](/lang/cpp11/defaulted_and_deleted_functions.md) | 自動定義される特殊関数の制御 | 4.4 | 3.0 | 12.0 | 2013: ムーブコンストラクタ・ムーブ代入演算子の`default`は不可<br/> 2015 |
| [委譲コンストラクタ](/lang/cpp11/delegating_constructors.md) | コンストラクタから他のコンストラクタに処理を委譲する | 4.7 | 3.0 | 14.0 | 2013 |
| [明示的な型変換演算子のオーバーロード](/lang/cpp11/explicit_conversion_operator.md) | 明示的な型変換が行われる場合にのみ呼び出される演算子をオーバーロードできるようにする | 4.5 | 3.0 | 14.0 | 2013 |
| [`friend`宣言できる対象を拡張](/lang/cpp11/extend_friend_targets.md) | テンプレートパラメータや型の別名を`friend`宣言 | 4.7 | 2.9 | 11.1 (partial) <br/> 12.0 | 2010 |
| [`extern template`](/lang/cpp11/extern_template.md) | テンプレートのインスタンス化抑止 | 3.3 | 2.9 | 11.1 | 6.0 |
| [継承コンストラクタ](/lang/cpp11/inheriting_constructors.md) | 基底クラスのコンストラクタを継承する | 4.8 | 3.3 | 15.0 | 2015 |
| [ラムダ式](/lang/cpp11/lambda_expressions.md) | 関数オブジェクトをその場に書く | 4.5 | 3.1 | 12.0 | 2010 (partial)<br/> 2012 |
| [ローカル型と無名型を、テンプレート引数として使用することを許可](/lang/cpp11/local_and_unnamed_type_as_template_arguments.md) | ローカルおよび無名として定義したクラスや列挙型を、テンプレート引数として渡せるようにする | 4.5 | 2.9 | 12.0 | 2010 |
| [`long long`型](/lang/cpp11/long_long_type.md) | 64ビット以上の大きさを持つ整数型 | 4.3 | 2.9 | 11.1 | 2003 |
| [インライン名前空間](/lang/cpp11/inline_namespaces.md) | ネストした名前空間に、透過的にアクセスする | 4.4 | 2.9 | 14.0 | 2015 |
| [`char16_t`と`char32_t`](/lang/cpp11/char16_32.md) | UTF-16とUTF-32の文字型 | 4.4 | 2.9 | 12.1 (Windows: partial) <br/> 12.1 (GNU/Linux, macOS)<br/> 14.0 | 2015<br/> 2010より組み込み型ではなく型の別名として存在する |
| [UTF-8文字列リテラル](/lang/cpp11/utf8_string_literals.md) | `char`の文字列をUTF-8エンコーディングするプレフィックス | 4.5 | 3.0 | 12.1 (Windows: partial) <br/> 12.1 (GNU/Linux, macOS)<br/> 14.0 | 2015 |
| [生文字列リテラル](/lang/cpp11/raw_string_literals.md) | 文字列リテラルにRプレフィックスを付けることで、エスケープシーケンスを無視する | 4.5 | 3.0 | 14.0 | 2013 |
| [ユーザー定義リテラル](/lang/cpp11/user_defined_literals.md) | リテラルのサフィックスをユーザー定義する | 4.7 | 3.1 | 15.0 | 2015 |
| [戻り値の型を後置する関数宣言構文](/lang/cpp11/trailing_return_types.md) | 以下のような形式での関数宣言<br/> `auto f(arg_types...) -> return_type` | 4.4 | 2.9 | 12.0 | 2010 |
| [`nullptr`](/lang/cpp11/nullptr.md) | ヌルポインタを表すポインタリテラル | 4.6 | 2.9 | 11.1 | 2010 |
| [テンプレートの右山カッコ](/lang/cpp11/right_angle_brackets.md) | `vector<basic_string<char>>`のように、`>>`をスペースを空けずに記述可能にする | 4.3 | 2.9 | 11.1 | 2005 |
| [右辺値参照・ムーブセマンティクス](/lang/cpp11/rvalue_ref_and_move_semantics.md) | 右辺値によるオーバーロード、およびそれによるリソースの所有権移動 | 4.3 (partial)<br/> 4.6 | 2.9 | 12.0 | 2010 (partial) ムーブコンストラクタと代入演算子の暗黙定義に対応していない。<br/> 2015 |
| [コンパイル時アサート](/lang/cpp11/static_assert.md) | コンパイル時に条件式が真であることを表明する | 4.3 | 2.9 | 11.1 | 2010 |
| [`enum`の先行宣言](/lang/cpp11/scoped_enum.md#extended-unscoped-enum) |  | 4.6 | 3.1 | 11.1 (partial)<br/> 14.0 | 2012 |
| [スコープを持つ列挙型](/lang/cpp11/scoped_enum.md) | 強い型付けとスコープを持つ列挙型 | 4.4 | 2.9 | 11.1 (partial)<br/> 14.0 | 2012 |
| [エイリアステンプレート](/lang/cpp11/alias_templates.md) | テンプレートによって型の別名を定義する | 4.7 | 3.0 | 12.1 | 2013 |
| [共用体の制限解除](/lang/cpp11/unrestricted_unions.md) | 共用体のメンバ変数として、クラスオブジェクトを持つ | 4.6 | 3.0 | 14.0(Linux系OSおよびMacのみ。Windowsは非対応) | 2015 |
| [可変引数テンプレート](/lang/cpp11/variadic_templates.md) | 任意の数のテンプレートパラメータを受け取れるようにする | 4.3 (partial)<br/> 4.4 | 2.9 | 12.1 | 2013 |
| [範囲for文](/lang/cpp11/range_based_for.md) | 配列やコンテナといった範囲を表すオブジェクトを、簡潔に走査する | 4.6 | 3.0 | 13.0 | 2012 |
| [`override`と`final`](/lang/cpp11/override_final.md) | メンバ関数のオーバーライド指定、および派生クラスでのオーバーロードを禁止する指定 | 4.7 | 2.9 | 14.0 | 2005 (partial): `override`のみ。`final`の代わりにsealedが存在する。ただし両者ともデストラクタには指定できない。<br/> 2012 |
| [属性構文](/lang/cpp11/attributes.md) | `[[attr]]`構文による、クラス、関数、変数の属性指定 | 4.8 | 3.3 | 12.1 | 2015 |
| [メンバ関数の左辺値／右辺値修飾](/lang/cpp11/ref_qualifier_for_this.md) | オブジェクトが左辺値／右辺値の場合のみ呼び出し可能であることの指定 | 4.8.1 | 2.9 | 14.0 | 2015 |
| [非静的メンバ変数の初期化](/lang/cpp11/non_static_data_member_initializers.md) | メンバ変数を、宣言と同時に初期値指定する | 4.7 | 3.0 | 14.0 | 2013 |
| [初期化子リスト](/lang/cpp11/initializer_lists.md) | 波括弧による初期化をユーザー定義する。`vector<int> v = {1, 2, 3};`など。 | 4.4 | 3.1 | 14.0 | 2013 |
| [一様初期化](/lang/cpp11/uniform_initialization.md) | コンストラクタ呼び出しを波カッコで行う。 `T x { a, b, c };` | 4.6 | 3.1 | 13.0(partial)<br/> 14.0 | 2013 |
| [`noexcept`](/lang/cpp11/noexcept.md) | 関数の例外指定、例外を投げる可能性のある式かbool値を返す演算子 | 4.6 | 3.0 | 13.0(partial)<br/>14.0 | 2015 |
| [任意の式によるSFINAE](/lang/cpp11/sfinae_expressions.md) | 特定の式が有効かどうかで、その関数をオーバーロード解決に含めるかどうかを決定する | 4.4 | 2.9 | 12.0 | 2015 Update 1 (partial)<br/> 2017 Update 7 |
| [スレッドローカルストレージ](/lang/cpp11/thread_local_storage.md) | スレッドごとに異なる静的記憶域に保持される変数 | 4.8 | 3.3 | 11.1 (partial) | 2010<br/> `__declspec(thread)`属性での部分サポート<br/> 2015 |
| [ブロックスコープを持つ`static`変数初期化のスレッドセーフ化](/lang/cpp11/static_initialization_thread_safely.md) | 関数ローカルで定義した`static`変数の初期化を、スレッドセーフにする | 4.0 | 2.9 | 11.0 (Lnux/macOS)<br/> 14.0 | 2015 |


各処理系のC++11実装状況ページ：

- 全体的な対応状況： [C++0xCompilerSupport](http://web.archive.org/web/20160327011707/https://wiki.apache.org/stdcxx/C++0xCompilerSupport)
- GCC： [C++11 Support in GCC](https://gcc.gnu.org/projects/cxx-status.html#cxx11)
- libstdc++ : [C++ 2011](https://gcc.gnu.org/onlinedocs/libstdc++/manual/status.html#status.iso.2011)
- Clang： [C++98 and C++11 Support in Clang](http://clang.llvm.org/cxx_status.html)
    - [C++ Defect Report Support in Clang](http://clang.llvm.org/cxx_dr_status.html)
- ICC : [C++11 Features Supported by Intel&#174; C++ Compiler](https://software.intel.com/en-us/articles/c0x-features-supported-by-intel-c-compiler)
- Visual C++ (MSVC):
    - [Visual C++ 言語への準拠](https://docs.microsoft.com/ja-jp/cpp/visual-cpp-language-conformance)
    - [Announcing: MSVC Conforms to the C++ Standard](https://blogs.msdn.microsoft.com/vcblog/2018/05/07/announcing-msvc-conforms-to-the-c-standard/)


## <a id="cpp14" href="#cpp14">C++14言語機能の実装状況</a>

| 言語機能                     | 説明 | [GCC][gcc] | [Clang][clang] | [ICC][icc] | [MSVC][msvc] |
|------------------------------|------|-----|-------|-----|------|
| [2進数リテラル](/lang/cpp14/binary_literals.md) | 2進数を表す`0b` or `0B`プレフィックスを付けた数値リテラルの記述を可能とする | 4.3(GNU)<br/> 4.9 | 3.2 | 11.0 | 2015 |
| [通常関数の戻り値型推論](/lang/cpp14/return_type_deduction_for_normal_functions.md) | 関数の戻り値型を`auto`にすることで、`return`文から戻り値の型を推論させる | 4.8(partial)<br/>4.9 | 3.3(partial)<br/> 3.4 | 15.0 | 2015 |
| [ラムダ式の初期化キャプチャ](/lang/cpp14/initialize_capture.md) | キャプチャに代入構文を導入し、一つの変数に複数のキャプチャ方法を指定可能にする | 4.9 | 3.4 | 15.0 | 2015 |
| [ジェネリックラムダ](/lang/cpp14/generic_lambdas.md) | ラムダ式のパラメータを`auto`にすることで、ジェネリックな関数呼び出し演算子を持つ関数オブジェクトを生成する | 4.9 | 3.4 | 16.0 | 2015 |
| [変数テンプレート](/lang/cpp14/variable_templates.md) | 変数定義時のテンプレート指定を可能にする。 | 5.1 | 3.4 | 16.0 | 2015 Update 2 |
| [`constexpr`の制限緩和](/lang/cpp14/relaxing_constraints_on_constexpr.md) | `if`文、`switch`文による条件分岐の許可。<br/>`for`文、`while`文、`do-while`文によるループの許可。<br/>`void`戻り値型の許可<br/>初期化を伴う変数宣言の許可。<br/>変数書き換えの許可。 | 5.1 | 3.3(partial) <br/> 3.4 | 16.0 | 2017 |
| [宣言時のメンバ初期化を持つ型の集成体初期化を許可](/lang/cpp14/brace_elision_in_array_temporary_initialization.md) | 一様初期化と初期化子リストを組み合わせた際、二重に波カッコが必要となっていた仕様を緩和し、波カッコを省略できるようにする | 5.1 | 3.3 | 16.0 | 2017 |
| [`[[deprecated]]`属性](/lang/cpp14/deprecated_attr.md) | 非推奨の機能であることを示す属性。 | 4.9 | 3.4 | 15.0<br/> (Linux/Mac OS) | 2015<br/>それ以前は`__declspec(deprecated)`で代替可能 |
| [数値リテラルの桁区切り文字](/lang/cpp14/digit_separators.md) | シングルクォーテーションで数値リテラルを桁区切りする。 | 4.9 | 3.4 | 16.0 | 2015 |
| [サイズ付きデアロケーション](/lang/cpp14/sized_deallocation.md) | サイズをとる`delete`演算子のオーバーロードを許可する。 | 5.1 | 3.4 | 16.0 | 2015 |


各処理系のC++14実装状況ページ：

- GCC: [C++14 Support in GCC](https://gcc.gnu.org/projects/cxx-status.html#cxx14)
- libstdc++: [C++ 2014](https://gcc.gnu.org/onlinedocs/libstdc++/manual/status.html#status.iso.2014)
- Clang: [C++98, C++11, and C++14 Support in Clang](http://clang.llvm.org/cxx_status.html)
- libc++: [libc++ C++1Y Status](http://libcxx.llvm.org/cxx1y_status.html)
- Visual C++ (MSVC):
    - [Visual C++ 言語への準拠](https://docs.microsoft.com/ja-jp/cpp/visual-cpp-language-conformance)
    - [Announcing: MSVC Conforms to the C++ Standard](https://blogs.msdn.microsoft.com/vcblog/2018/05/07/announcing-msvc-conforms-to-the-c-standard/)
- ICC: [C++14 Features Supported by Intel C++ Compiler](https://software.intel.com/en-us/articles/c14-features-supported-by-intel-c-compiler)
    - [Intel (R) Parallel Studio XE 2016 Beta program has begun](https://software.intel.com/en-us/forums/topic/549502)


## <a id="cpp17" href="#cpp17">C++17言語機能の実装状況</a>

| 言語機能 | 説明 | [GCC][gcc] | [Clang][clang] | [ICC][icc] | [MSVC][msvc] |
|----------|------|-----|-------|-----|------|
| [メッセージなしの`static_assert`](/lang/cpp17/extending_static_assert.md) | デフォルトの表明メッセージを使用する | 6 | 3.5 | 18.0 | 2017 |
| [トライグラフを削除](/lang/cpp17/removing_trigraphs.md) | | 5.1 | 3.5 | 19.1 | 2010 |
| [テンプレートテンプレートパラメータに`typename`を許可](/lang/cpp17/allow_typename_in_a_template_template_parameter.md) | `class`キーワードしか使用できなかった部分に、`typename`を許可 | 5.0 | 3.5 | 17.0 | 2015 |
| [単一要素初期化子リストを`auto`で受け取った場合の型を変更](/lang/cpp17/new_rules_for_auto_deduction_from_braced-init-list.md) | `initializer_list<T>`だったのを`T`に変更 | 5 | 3.8 | 17.0 | 2015 |
| [畳み込み式](/lang/cpp17/folding_expressions.md) | パラメータパックに対する2項演算の集積処理 | 6 | 3.6 | 19.0 | 2017 Update 5 |
| [UTF-8文字リテラル](/lang/cpp17/utf8_character_literals.md) | 文字列リテラルだけでなく、文字リテラルにもUTF-8指定できるようにする | 6 | 3.6 | 17.0 | 2015 |
| [入れ子名前空間の定義](/lang/cpp17/nested_namespace.md) | `namespace A::B {}`のように、入れ子の名前空間を簡単に定義できるようにする | 6 | 3.6 | 17.0 | 2015 Update 3 |
| [名前空間と列挙子に属性の付加を許可](/lang/cpp17/attributes_for_namespaces_and_enumerators.md) | 名前空間の定義と、列挙型の各要素の定義に、属性を付けられるようにする | 名前空間は4.0<br/>列挙子は6 | 3.6 | 17.0 | 2015 |
| [全ての非型テンプレート引数の定数式評価を許可](/lang/cpp17/allow_constant_evaluation_for_all_non-type_template_arguments.md) | ポインタの定数式評価として、配列からポインタへの変換や、関数から関数ポインタへの変換などを許可 | 6 | 3.6 | 19.1 | 2017 Update 5 |
| [非推奨だった`register`キーワードを削除](/lang/cpp17/remove_deprecated_use_of_the_register_keyword.md) | | 7 | 3.8 | 18.0 | 2017 Update 3 |
| [非推奨だった`bool`型オブジェクトに対するインクリメントの仕様を削除](/lang/cpp17/remove_deprecated_increment_of_bool.md) | | 7 | 3.8 | 18.0 | 2017 Update 3 |
| [例外仕様を型システムの一部にする](/lang/cpp17/exception_spec_be_part_of_the_type_system.md) | | 7 | 4 | 18.0 | 2017 Update 5 |
| [プリプロセッサでの条件式`__has_include`](/lang/cpp17/has_include.md) | 対象のインクルードファイルが存在するかをプリプロセス時に判定する | 5.0 | 3.0 | 18.0 | 2017 Update 3 |
| [継承コンストラクタの新仕様][P0136R1] | デフォルト引数を引き継ぐようにした | 7 | 3.9 | No | 2017 Update 7 |
| [`[[fallthrough]]`属性](/lang/cpp17/fallthrough.md) | `case`節で`break`や`return`を書かなかった場合に、それが意図したフォールスルーであることをコンパイラに伝える属性 | 7 | 3.9 | 18.0 | 2017 |
| [`[[nodiscard]]`属性](/lang/cpp17/nodiscard.md) | 関数の戻り値を無視してはならないことをユーザーに伝える属性 | 4.8からは`[[gnu::warn_unused_result]]`を使用すること<br/> 7からサポート | 3.9 | 18.0 | 2017 Update 3 |
| [`[[maybe_unused]]`属性](/lang/cpp17/maybe_unused.md) | 使用しない可能性がある変数であることをコンパイラに伝える属性 | 4.8からは`[[gnu::unused]]`を使用すること<br/> 7からサポート | 3.9 | 18.0 | 2017 Update 3 |
| [基底クラスのメンバ変数を集成体初期化するための波カッコを省略できるようにする][P0017R1] | 基底クラスのメンバを集成体初期化するために、`derived d {{42}};`の代わりに`derived d {42};`と書けるようにする | 7 | 3.9 | 19.1 | 2017 Update 7 |
| [ラムダ式を`constexpr`として使用できるようにする](/lang/cpp17/constexpr_lambda.md) | ラムダ式の関数オブジェクトが定数式の文脈で使用された場合に、それがコンパイル時に評価されるようにする | 7 | 5 | 19.0 | 2017 Update 3 |
| [範囲for文のための`begin()`と`end()`関数が、異なる型を返すことを許可](/lang/cpp17/generalizing_the_range-based_for_loop.md) | `begin()`と`end()`が異なるイテレータ型を返せるようにすることで、終端イテレータを定義しやすくする | 6 | 3.9 | 18.0 | 2017 |
| [ラムダ式での`*this`のコピーキャプチャ](/lang/cpp17/lambda_capture_of_this_by_value.md) | キャプチャリストに`*this`を指定することで、`*this`をコピーキャプチャする | 7 | 3.8 | 19.0 | 2017 Update 3 |
| [`enum class`変数の初期値として整数を指定する際の規則を調整](/lang/cpp17/construction_enum_class_values.md) | キャストを使用することなく整数を初期値として使用し、`E e{0};`のような初期化を許可 | 7 | 1.9 | 19.0 | 2017 Update 3 |
| [浮動小数点数の16進数リテラル](/lang/cpp17/hexadecimal_floating_literals.md) | `hexfloat`マニピュレータや`printf()`の16進数出力に合わせて、浮動小数点数のリテラルも16進数表記できるようにする | 3.0 | 3.0 | 18.0 | 2017 Update 5 |
| [属性の名前空間指定に繰り返しをなくす](/lang/cpp17/using_attribute_namespaces.md) | `[[using CC: opt(1), debug]]`のように属性の名前空間宣言をまとめて行う | 7 | 3.9 | 18.0 | 2017 Update 3 |
| [アライメント指定されたデータの動的メモリ確保](/lang/cpp17/dynamic_memory_allocation_for_over-aligned_data.md) | `operator new`と`operator delete`でアライメント値を取得できるようにする | 7 | 4 | No | 2017 Update 5 |
| [クラステンプレートのテンプレート引数推論](/lang/cpp17/type_deduction_for_class_templates.md) | コンストラクタの引数からクラスのテンプレート引数を推論できるようにする | 7 | 5 | 19.1 | 2017 Update 7 |
| [非型テンプレート引数の`auto`宣言](/lang/cpp17/declaring_non-type_template_arguments_with_auto.md) | `template <typename T, T x>`という冗長なコードを`template <auto x>`のようにして受けられるようにし、<br/> `X<3>; X<true>; X<'a'>`のように定数を簡潔に渡せるようにする | 7 | 4 | 19.1 | 2017 Update 7 |
| [値のコピー省略を保証](/lang/cpp17/guaranteed_copy_elision.md) | 一時オブジェクトをコピーする際に、単純な値を持つクラスであればコピーが省略されることを保証する | 7 | 4 | 19.1 | 2017 Update 6 |
| [厳密な式の評価順](/lang/cpp17/expression_evaluation_order.md) | 式の項が評価される順序を厳密に規定する。<br/> `b = a;`の式が右から順番(a, bの順)に評価される | 7 | 4 | 19.1 | 2017 Update 7 |
| [不明な属性を無視する](/lang/cpp17/non_standard_attributes.md) | 実装が知らない名前空間の属性は無視する | 4.8 | 3.0 | 18.0 | 2015 |
| [constexpr if文](/lang/cpp17/if_constexpr.md) | `if constexpr(cond)`とすることで、そのif文はコンパイル時に処理される | 7 | 3.9 | 19.0 | 2017 Update 3 |
| [処理の進行保証][P0296R2] | 並行処理に関して「処理の進行」を明確に定義<br/> (TODO:言葉の定義だけなので実装状況ページからは取り除く) | No | No | No | No |
| [インライン変数](/lang/cpp17/inline_variables.md) | インライン指定を関数だけでなく変数にも指定できるようにする | 7 | 3.9 | 19.0 | 2017 Update 5 |
| [templated entityという用語を導入][P0391R0] | (TODO:言葉の定義だけなので実装状況ページからは取り除く) | - | - | - | - |
| [構造化束縛](/lang/cpp17/structured_bindings.md) | タプルやユーザー定義型を分解して受け取れるようにする<br/> `tuple<int, string> f();` <br/> `const auto [a, b] = f(); // aはintの値、bはstringの値` | 7 | 4 | 18.0 | 2017 Update 3 |
| [if文とswitch文の条件式と初期化を分離](/lang/cpp17/selection_statements_with_initializer.md) | `if (init; condition)`のように初期化と条件式を分けて記述できるようにする | 7 | 3.9 | 18.0 | 2017 Update 3 |
| [参照メンバをもつクラスの置き換え](/lang/cpp17/replacement_of_class_objects_containing_reference_members.md) | 参照型メンバや`const`データメンバを含むクラスについてこれまで結果は未定義とされていた配置`new`によるオブジェクトの置き換えを条件付きで可能とする | 7 | 6.0 | No | 2017 Update 7 |
| [非推奨だった例外仕様を削除](/lang/cpp17/remove_deprecated_exception_specifications.md) | `noexcept`が入ったことによって非推奨になった`throw`キーワードによる例外仕様を削除 | 7 | 4 | No | 2017 Update 5 |
| [using宣言でのパック展開](/lang/cpp17/pack_expansions_in_using.md) | パラメータパックの型を基底クラスとして指定した場合に、`using`宣言に基底クラスのパラメータパックを指定できるようにする | 7 | 4 | No | 2017 Update 7 |
| [クラステンプレート引数の推論仕様を調整][P0512R0] | | 8 | 5.0 | No | 2017 Update 7 |
| [Committee Draftに対するNational Body Commentへの対応][P0490R0] | | - | - | - | - |
| [テンプレートテンプレート引数のマッチングにおいて、互換性のあるテンプレートを除外][P0522R0] | | 7 | 4 (partial) | 19.1 | 2017 Update 5 |


[P0136R1]: http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0136r1.html
[P0017R1]: http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0017r1.html
[P0296R2]: http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0296r2.html
[P0391R0]: http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0391r0.html
[P0512R0]: http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0512r0.pdf
[P0490R0]: http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0490r0.html
[P0522R0]: http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0522r0.html


各処理系のC++17実装状況ページ：

- GCC: [C++17 Support in GCC](https://gcc.gnu.org/projects/cxx-status.html#cxx17)
- Clang: [C++ Support in Clang](http://clang.llvm.org/cxx_status.html)
- libc++ : [libc++ C++1z Status](http://libcxx.llvm.org/cxx1z_status.html)
- Visual C++ (MSVC):
    - [Visual C++ 言語への準拠](https://docs.microsoft.com/ja-jp/cpp/visual-cpp-language-conformance)
    - [Announcing: MSVC Conforms to the C++ Standard](https://blogs.msdn.microsoft.com/vcblog/2018/05/07/announcing-msvc-conforms-to-the-c-standard/)
- ICC: [C++17 Features Supported by Intel C++ Compiler](https://software.intel.com/en-us/articles/c17-features-supported-by-intel-c-compiler)


## <a id="cpp20" href="#cpp20">C++20言語機能の実装状況</a>

| 言語機能 | 説明 | [GCC][gcc] | [Clang][clang] | [ICC][icc] | [MSVC][msvc] |
|----------|------|-----|-------|-----|------|
| [ビットフィールドのメンバ変数初期化](/lang/cpp20/default_member_initializers_for_bit_fields.md) | ビットフィールドメンバ変数のデフォルト値を設定する構文を追加する | 8 | 6.0 | | 2019 Update 5 |
| [ラムダ式のキャプチャとして`[=, this]`を許可する](/lang/cpp20/allow_lambda_capture_equal_this.md) | デフォルトコピーキャプチャと`this`ポインタのコピーキャプチャを両方指定できるようにする | 8 | 6.0 | | 2019 Update 1 |
| [`[=]`による`this`の暗黙のキャプチャを非推奨化](/lang/cpp20/deprecate_implicit_capture_of_this_via_defcopy.md) | コピーのデフォルトキャプチャでは、`this`ポインタをキャプチャされなくする | 9 | | | 2019 Update 2 |
| [ジェネリックラムダのテンプレート構文](/lang/cpp20/familiar_template_syntax_for_generic_lambdas.md) | ジェネリックラムダでテンプレートパラメータを定義できるようにする | 8 | 9.0 | | 2019 Update 2 |
| [`const`修飾されたメンバポインタの制限を修正](/lang/cpp20/fixing_const_qualified_pointers_to_members.md) | `.*`演算子での左辺値の`const`メンバ関数呼び出しを許可する | 8 | 6.0 | | 2015 |
| [可変引数が空でない場合のトークン置換](/lang/cpp20/va_opt.md) | プリプロセッサの置換で可変引数が空の場合に余計なカンマが付いてしまう問題に対処 | 8 (partial, `#__VA_OPT__`による文字列化が未サポート) | 6.0<br/> 9.0 ([p1042](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2018/p1042r1.html)) | | 2019 Update 5 |
| [指示付き初期化](/lang/cpp20/designated_initialization.md) | | 8 | 6.0 (partial) | | 2019 Update 1 |
| [コンセプト](/lang/cpp20/concepts.md) | テンプレートパラメータに対する制約を行う | 10 | 10.0 (partial) | | 2019 Update 3 |
| [初期化式をともなう範囲for文](/lang/cpp20/range-based_for_statements_with_initializer.md) | 範囲for文スコープで使用する変数の初期化のための構文を追加 | 9 | 8.0 | | 2019 Update 5 |
| [暗黙のラムダキャプチャを簡略化](/lang/cpp20/simplifying_implicit_lambda_capture.md.nolink) | | 8 | | | 2019 Update 2 |
| [関数テンプレートに明示的に型指定した場合にADLで見つからない問題を修正](/lang/cpp20/adl_and_function_templates_that_are_not_visible.md) | 名前空間内の関数テンプレートをテンプレート引数指定かつ非修飾・ADLで正しく呼び出せるよう修正 | 9 | 9.0 | | 2019 Update 1 |
| [デフォルトのコピーコンストラクタと非`const`なコンストラクタが衝突する問題を修正](/lang/cpp20/resolving_const_mismatch_with_defaulted_copy_constructor.md.nolink) | | 9 | 8.0 | | partial |
| [積極的でない`constexpr`関数のインスタンス化](/lang/cpp20/less_eager_instantiation_of_constexpr_functions.md.nolink) | | 9 | | | |
| [一貫比較](/lang/cpp20/consistent_comparison.md) | 三方比較演算子によって比較演算子の自動生成を行うようにする | 10 | 8.0 (partial) | | 2019 |
| [特殊化のアクセスチェック](/lang/cpp20/access_checking_on_specializations.md.nolink) | | Yes | partial | | 2019 Update 6 |
| [状態を持たないラムダ式を、デフォルト構築可能、代入可能とする](/lang/cpp20/default_constructible_and_assignable_stateless_lambdas.md) | キャプチャしていないラムダ式をデフォルト構築・代入可能にする | 9 | 8.0 | | 2019 Update 2 |
| [PODを非推奨化](/lang/cpp20/deprecate_pod.md) | PODという用語を非推奨化する | | | | 2019 Update 5 |
| [評価されない文脈でのラムダ式](/lang/cpp20/wording_for_lambdas_in_unevaluated_contexts.md) | 評価されない文脈でもラムダ式を書くことができるようにする | 9 | | | 2019 Update 8 |
| [空オブジェクトを言語サポート](/lang/cpp20/language_support_for_empty_objects.md) | `[[no_unique_address]]`属性を導入し、空の型のオブジェクトをほかのオブジェクトと共有する最適化を許可する | 9 | 9.0 | | |
| [範囲for文がカスタマイゼーションポイントを見つけるルールを緩和](/lang/cpp20/relaxing_the_range_for_loop_customization_point_finding_rules.md) | `begin()`/`end()`メンバ関数のどちらかが見つからなかった場合に非メンバ関数の`begin()`/`end()`を探しにいく | 8 | | | 2019 Update 5 |
| [friend指定された関数内から構造化束縛を使用して非公開メンバ変数にアクセスすることを許可](/lang/cpp20/allow_structured_bindings_to_accessible_members.md) | 構造化束縛の仕様として公開メンバ変数のみを取り出せるようになっていたが、friend指定された関数からは非公開メンバ変数にもアクセスできるようにする | 8 | 8.0 | | 2019 |
| [構造化束縛がカスタマイゼーションポイントを見つけるルールを緩和](/lang/cpp20/relaxing_the_structured_bindings_customization_point_finding_rules.md) | 非テンプレートの`get()`メンバ関数が見つかった場合は、非メンバ関数の`get()`を探しにいく | 8 | 8.0 | | 2019 |
| [型の文脈で`typename`の省略を許可](/lang/cpp20/down_with_typename.md) | 型しか現れない文脈では、依存名を解決するための`typename`キーワードを省略できるようにする | 9 | | | |
| [ラムダ式の初期化キャプチャでのパック展開を許可](/lang/cpp20/allow_pack_expansion_in_lambda_init_capture.md) | `[...args = std::move(args)]`のようなキャプチャを許可 | 8 | 9.0 | | 2019 Update 2 |
| [確率が高い分岐と低い分岐を伝える属性 `[[likely]]`, `[[unlikely]]`](/lang/cpp20/likely_and_unlikely_attributes.md) | 条件分岐の最適化ヒントを与える属性 | 9 (partial, `switch` 文のみ可能)<br/> 10 | 12.0 | | 2019 Update 6 |
| [抽象型のチェック](/lang/cpp20/checking_for_abstract_class_types.md.nolink) | 関数の宣言段階では、パラメータおよび戻り値型が抽象型かどうかをチェックしないようにする | 11 | | | 2019 Update 5 |
| [非型テンプレートパラメータとしてクラス型を許可する](/lang/cpp20/class_types_in_non-type_template_parameters.md) | 定数式として使用できる型を広く非型テンプレートパラメータとして使用できるようにする | 9 | partial | | 2019 Update 6 |
| [可変長データを扱うクラスの効率的な`delete`](/lang/cpp20/efficient_sized_delete_for_variable_sized_classes.md.nolink) | クラスの`delete`演算子が呼び出される前にデストラクタが呼ばれないようにするオプションを追加 | 9 | 6.0 | | 2019 Update 7 |
| [定数式からの仮想関数の呼び出しを許可](/lang/cpp20/allow_virtual_function_calls_in_constant_expressions.md) | 仮想関数に`constexpr`を付けられない制限を解除 | 9 | 9.0 | | |
| [定数式での`dynamic_cast`、多態的な`typeid`を許可](/lang/cpp20/allowing_dynamic_cast_polymorphic_typeid_in_constant_expressions.md.nolink) | 定数式での動的多態を許可 | 10 | 9.0 | | |
| [constexpr関数内でのtry-catchブロックを許可](/lang/cpp20/try-catch_blocks_in_constexpr_functions.md) | constexpr関数内でtry-catchブロックを書けるようにする | 9 | 8.0 | | 2019 Update 5 |
| [即時関数](/lang/cpp20/immediate_functions.md) | `consteval`キーワードを追加し、常に定数式評価されるよう指定できるようにする | | | | |
| [定数式内での共用体のアクティブメンバの変更を許可](/lang/cpp20/changing_the_active_member_of_a_union_inside_constexpr.md.nolink) | 共用体メンバの書き換えを定数式内で行えるようにする | 9 | 9.0 | | 2017 |
| [ユーザー宣言したコンストラクタを持つクラスの集成体初期化を禁止](/lang/cpp20/prohibit_aggregates_with_user-declared_constructors.md) | コンストラクタが`delete`／`default`宣言されているクラスを、集成体初期化によってコンストラクタ呼び出しを回避して構築できてしまっていた技法を禁止 | 9 | 8.0 | | 2019 |
| [関数を条件付きで`explicit`にする構文を追加](/lang/cpp20/explicit_bool.md) | `explicit(true)`のように`explicit`に真理値パラメータを指定できるようにする | 9 | 9.0 | | 2019 Update 2 |
| [符号付き整数型が2の補数表現であることを規定](/lang/cpp20/signed_integers_are_twos_complement.md) | 符号付き整数型のビット表現を2の補数に規定する | 9 | 9.0 | | |
| [UTF-8エンコーディングされた文字の型として`char8_t`を追加](/lang/cpp20/char8_t.md) | UTF-8エンコードされた文字かどうかでオーバーロード・特殊化をできるようにする | 9 | 7 (`-fchar8_t`オプションが必要) | | 2019 Update 2 |
| [入れ子名前空間定義でのインライン名前空間](/lang/cpp20/nested_inline_mamespaces.md) | `namespace ns1::inline ns2::ns3 {}`のように、入れ子名前空間を定義する式にインライン名前空間の指定を含められるようにする | 9 | 8.0 |  | 2019 Update 7 |
| [構造化束縛を拡張して通常の変数宣言のように使用できるようにする](/lang/cpp20/extending_structured_bindings_to_be_more_like_variable_declarations.md) | 記憶域指定子として`static`と`thread_local`の指定を許可 | 10 | 8.0 (partial) | | 2019 Update 4 |
| [構造化束縛した変数の参照キャプチャを許可](/lang/cpp20/reference_capture_of_structured_bindings.md) | 構造化束縛をした変数は特殊な扱いのためラムダ式で参照キャプチャできない規定となっていたがこれを許可する | 8 | 8.0 (partial) | | 2017 Update 3 |
| [丸カッコの値リストからの集成体初期化を許可](/lang/cpp20/allow_initializing_aggregates_from_a_parenthesized_list_of_values.md) | `T x{1, 2, 3};`と同様に`T x(1, 2, 3);`でも集成体初期化できるようにする | 10 | | | 2019 Update 8 |
| [`new`式での配列要素数の推論](/lang/cpp20/array_size_deduction_in_new-expressions.md) | `double* p = new double[]{1,2,3};`を許可 | 11 | | | 2019 Update 7 |
| [`char16_t`と`char32_t`の文字・文字列リテラルを、文字コードUTF-16/32に規定](/lang/cpp20/make_char16t_char32t_string_literals_be_utf16_32.md) | `__STDC_UTF_16__`、`__STDC_UTF_32__`の定義に関係なく、`char16_t`、`char32_t`のリテラルをUTF-16/32文字コードに規定する | 10 | Yes | | 2015 |
| [モジュール](/lang/cpp20/modules.md) | ヘッダファイル・ソースファイル、インクルードに変わる仕組みとしてモジュールを導入する | 11 (`-fmodules-ts`が必要) | 8.0 partial (`-fmodules`, `-fmodules-ts`が必要) | | 2019 Update 8 |
| [コルーチン](/lang/cpp20/coroutines.md) | 関数実行を中断・再開する仕組みとしてコルーチンを導入する | 10 (`-fcoroutines`が必要) | 8.0 (partial) | | 2019 Update 8 |
| [添字演算子内でのカンマ演算子の使用を非推奨化](/lang/cpp20/deprecate_uses_of_the_comma_operator_in_subscripting_expressions.md) | `ar[i, j]`を非推奨化。`ar[(i, j)]`はOK | 10 | 9.0 | | 2019 Update 5 |
| [constexprの文脈でのトリビアルなデフォルト初期化を許可](/lang/cpp20/permitting_trivial_default_initialization_in_constexpr_contexts.md.nolink) | constexpr関数内でのデフォルト初期化を許可し、未初期化値を読むことのみ禁止する | 10 | 10.0 | | 2019 Update 7 |
| [条件付きで特殊メンバ関数をトリビアルに定義するように](/lang/cpp20/conditionally_trivial_special_member_functions.md.nolink) | 制約によってトリビアルな特殊メンバ関数と非トリビアルな特殊メンバ関数をオーバーロードできるようにする | | | | |
| [`[[nodiscard]]`属性に理由となる文字列を付加できるようにする](/lang/cpp20/nodiscard_should_have_a_reason.md) | 関数の戻り値を無視してはならない理由を関数宣言に持たせ、警告メッセージに役立てる | 10 | 9.0 | | 2019 Update 5 |
| [スコープ付き列挙型のusing宣言](/lang/cpp20/using_enum.md) | `using enum EnumType;`もしくは`using EnumType::enumerator`とすることで、列挙値のスコープ指定を省略できるようにする | 11 | | | 2019 Update 4 |
| [集成体クラステンプレートのテンプレート引数推論](/lang/cpp20/class_template_argument_deduction_for_aggregates.md) | クラステンプレートのテンプレート引数推論はコンストラクタ引数から推論されるが、集成体初期化からも推論できるようにする | 10 | | | 2019 Update 7 |
| [constexpr関数内で未評価のインラインアセンブリを許可することによる組み込み関数のconstexpr有効化](/lang/cpp20/enabling_constexpr_intrinsics_by_permitting_unevaluated_inline-assembly_in_constexpr_functions.md.nolink) | コンパイル時に評価されない場合にconstexpr関数にasm定義を含めることを許可 | 10 | 10.0 | | 2019 Update 9 |
| [要素数不明の配列への変換を許可](/lang/cpp20/permit_conversions_to_arrays_of_unknown_bound.md) | 要素数が判明している配列から、要素数が不明の配列への変換を許可 | 10 | | | 2019 Update 7 |
| [コンパイル時初期化を強制する`constinit`キーワードを追加](/lang/cpp20/constinit.md) | 初期化のみコンパイル時におわらせたい場合に使用する | 10 | 10.0 | | |
| [ほとんどの`volatile`を非推奨化](/lang/cpp20/deprecating_volatile.md.nolink) | `volatile`の有用な機能のみを残し、効果が疑わしい、または壊れている機能を非推奨化する | 10 | 10.0 | | 2019 Update 7 |
| [エイリアステンプレート経由でのクラステンプレートのテンプレート引数推論](/lang/cpp20/class_template_argument_deduction_for_alias_templates.md) | エイリアステンプレートからクラステンプレートのテンプレート引数を推論できるようにする | 10 | | | 2019 Update 7 |
| [可変サイズをもつコンテナの`constexpr`化](/lang/cpp20/more_constexpr_containers.md.nolink) | `constexpr`記憶域をもつメモリアロケータの存在を考慮することで、可変サイズをもつコンテナをコンパイル時に使用できるようにする | 10 | 10.0 | | 2019 Update 9 |


各処理系のC++20実装状況ページ：

- GCC: [C++20 Support in GCC](https://gcc.gnu.org/projects/cxx-status.html#cxx20)
- Clang: [C++ Support in Clang](http://clang.llvm.org/cxx_status.html)
- libstdc++: [C++ 2020 Implementation Status](https://gcc.gnu.org/onlinedocs/libstdc++/manual/status.html#status.iso.2020)
- libc++: [libc++ C++2a Status](http://libcxx.llvm.org/cxx2a_status.html)
- Visual C++ (MSVC):
    - [Visual C++ 言語への準拠](https://docs.microsoft.com/ja-jp/cpp/visual-cpp-language-conformance)
    - [次リリース情報 - Visual Studio 2019 change log](https://github.com/microsoft/STL/wiki/Changelog)


## <a id="cpp23" href="#cpp23">C++23言語機能の実装状況</a>

| 言語機能 | 説明 | [GCC][gcc] | [Clang][clang] | [ICC][icc] | [MSVC][msvc] |
|----------|------|------------|----------------|------------|--------------|
| [(符号付き)`size_t`リテラルのためのサフィックス](/lang/cpp23/literal_suffix_for_signed_size_t.md) | `42z`/`42Z`とすることで`size_t`に対応する符号付き整数型のリテラルとする | 11 | - | - | - |
| [部分特殊化の汎用化仕様](/lang/cpp23/generalized_wording_for_partial_specializations.md.nolink) | 変数テンプレートの部分特殊化を許可するために部分特殊化の仕様を汎用化 | - | - | - | - |
| [文字・文字列リテラル中の数値・ユニバーサルキャラクタのエスケープに関する問題解決](/lang/cpp23/numeric_and_universal_character_escapes_in_character_and_string_literals.md.nolink) | | - | - | - | - |
| [スコープと名前ルックアップの仕様整理](/lang/cpp23/declarations_and_where_to_find_them.md.nolink) | 複雑で不完全になっているスコープと名前ルックアップの仕様を整理し、一部の問題を解決する | - | - | - | - |
| [ラムダ式で`()`を省略できる条件を緩和](/lang/cpp23/down_with_lambda_parens.md.nolink) | キャプチャや修飾をともなってもパラメータリストが空であれば`()`を省略できる | 11 | 13 | - | - |


各処理系のC++20実装状況ページ：

- GCC: [C++23 Support in GCC](https://gcc.gnu.org/projects/cxx-status.html#cxx23)
- Clang: [C++2b implementation status](https://clang.llvm.org/cxx_status.html#cxx23)

[gcc]: ./implementation.md#gcc
[clang]: ./implementation.md#clang
[icc]: ./implementation.md#icc
[msvc]: ./implementation.md#visual_cpp

