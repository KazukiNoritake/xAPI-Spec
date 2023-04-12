# Experience API
## Advanced Distributed Learning (ADL) Co-Laboratories

>#### License

>"Copyright 2013 Advanced Distributed Learning (ADL) Initiative, U.S. Department of Defense

>Licensed under the Apache License, Version 2.0 (the "License"). You may not use this file except 
>in compliance with the License. You may obtain a copy of the License at
>http://www.apache.org/licenses/LICENSE-2.0

>Unless required by applicable law or agreed to in writing, software distributed under the License 
>is distributed on an "AS IS" BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express 
>or implied. See the License for the specific language governing permissions and limitations under 
>the License."

>This document was authored by members of the Experience API Working Group (see 
>list in [CONTRIBUTING.md](CONTRIBUTING.md#contributors)) in support of the Office of the Deputy Assistant Secretary of 
>Defense (Readiness) Advanced Distributed Learning (ADL) Initiative. Please 
>send all feedback and inquiries to helpdesk@adlnet.gov  

## Table of Contents
*	Part One:	[About the Experience API](./xAPI-About.md#partone)  
	*	1.0.	[Introduction](./xAPI-About.md#introduction-partone) 
	*	2.0.	[How To Use This Document](./xAPI-About.md#readingguidelines)  
		*	2.1.	[MUST / SHOULD / MAY](./xAPI-About.md#def-must-should-may)  
	 	*	2.2.	[Guidelines for Interpreting Descriptive Text and Tables](./xAPI-About.md#interpret-text-table)  
	*	3.0.	[Serialization and JavaScript Object Notation](./xAPI-About.md#json)
	*	4.0.	[Definitions](./xAPI-About.md#definitions) 
	*	5.0.	[xAPI Components](./xAPI-About.md#xapi-components) 
	*	6.0.	[Extending xAPI](./xAPI-About.md#extending-xapi) 
	*	7.0.	[Profiles and Communities of Practice](./xAPI-About.md#COPs)  
	*	[Appendices](./xAPI-About.md#append1)  
		*	[Appendix A: Revision History](./xAPI-About.md#Appendix1A)  
		*	[Appendix B: cmi5 Example](./xAPI-About.md#Appendix1B)  
*	Part Two:	[Experience API Data](./xAPI-Data.md#parttwo)  
	*	1.0.	[Documents](./xAPI-Data.md#documents) 
	*	2.0.	[Statements](./xAPI-Data.md#statements)  
		*	2.1.	[Purpose](./xAPI-Data.md#statement-purpose)  
	 	*	2.2.	[Formatting Requirements](./xAPI-Data.md#dataconstraints) 
	 	*	2.3.	[Statement Lifecycle](./xAPI-Data.md#lifecycle) 
		 	*	2.3.1.	[Statement Immutability](./xAPI-Data.md#statement-immutability-and-exceptions) 
		 	*	2.3.2.	[Voiding](./xAPI-Data.md#voided) 
   		*	2.4.	[Statement Properties](./xAPI-Data.md#statement-properties)  
	        *	2.4.1.	[ID](./xAPI-Data.md#stmtid)  
	        *	2.4.2.	[Actor](./xAPI-Data.md#actor)  
	        *	2.4.3.	[Verb](./xAPI-Data.md#verb)  
	        *	2.4.4.	[Object](./xAPI-Data.md#object)  
	        *	2.4.5.	[Result](./xAPI-Data.md#result)  
	        *	2.4.6.	[Context](./xAPI-Data.md#context)  
	        *	2.4.7.	[Timestamp](./xAPI-Data.md#timestamp)  
	        *	2.4.8.	[Stored](./xAPI-Data.md#stored)  
	        *	2.4.9.	[Authority](./xAPI-Data.md#authority)  
	        *	2.4.10.	[Version](./xAPI-Data.md#version)  
	        *	2.4.11.	[Attachments](./xAPI-Data.md#attachments)  
    	*	2.5.	[Retrieval of Statements](./xAPI-Data.md#retrieval)   
    	*	2.6.	[Signed Statements](./xAPI-Data.md#signature)  
	*	3.0.	[Metadata](./xAPI-Data.md#metadata)
		*	3.1.	[IRI Requirements](./xAPI-Data.md#iri-requirements)  
		*	3.2.	[Hosted Metadata](./xAPI-Data.md#miscmeta)  
    *	4.0.	[Special Data Types and Rules](./xAPI-Data.md#special-data)  
		*	4.1.	[Extensions](./xAPI-Data.md#miscext) 
		*	4.2.	[Language Maps](./xAPI-Data.md#lang-maps)
		*	4.3.	[IRIs](./xAPI-Data.md#iris)
		*	4.4.	[UUIDs](./xAPI-Data.md#uuids)
		*	4.5.	[ISO 8601 Timestamps](./xAPI-Data.md#timestamps)
		*	4.6.	[ISO 8601 Durations](./xAPI-Data.md#durations)
	*	[Appendices](./xAPI-Data.md#append2)  
		*	[Appendix A: Example Statements](./xAPI-Data.md#Appendix2A)  
		*	[Appendix B: Example statement objects of different types](./xAPI-Data.md#Appendix2B)  
		*	[Appendix C: Example definitions for Activities of type "cmi.interaction"](./xAPI-Data.md#Appendix2C)  	
		*	[Appendix D: Example Signed Statement](./xAPI-Data.md#Appendix2D)  
*	Part Three:	[Data Processing, Validation, and Security](./xAPI-Communication.md#partthree)  
	*	1.0.	[Requests](./xAPI-Communication.md#requests)
		*	1.1.	[HEAD Request Implementation](./xAPI-Communication.md#httphead)  
	 	*	1.2.	[Headers](./xAPI-Communication.md#headers) 
	 	*	1.3.	[Alternate Request Syntax](./xAPI-Communication.md#alt-request-syntax) 
	 	*	1.4.	[Encoding](./xAPI-Communication.md#encoding) 
	 	*	1.5.	[Content Types](./xAPI-Communication.md#content-types) 
	        *	1.5.1.	[Application/JSON](./xAPI-Communication.md#applicationjson) 
	        *	1.5.2.	[Multipart/Mixed](./xAPI-Communication.md#multipartmixed)
	*	2.0.	[Resources](./xAPI-Communication.md#datatransfer)   
	 	*	2.1.	[Statement Resource](./xAPI-Communication.md#stmtres) 
	 	*	2.2.	[Documents Resources](./xAPI-Communication.md#doctransfer) 
	 	*	2.3.	[State Resource](./xAPI-Communication.md#stateres) 
	 	*	2.4.	[Agents Resource](./xAPI-Communication.md#agentsres) 
	 	*	2.5.	[Activities Resource](./xAPI-Communication.md#activitiesres) 
	 	*	2.6.	[Agent Profile Resource](./xAPI-Communication.md#agentprofres) 
	 	*	2.7.	[Activity Profile Resource](./xAPI-Communication.md#actprofres) 
	 	*	2.8.	[About Resource](./xAPI-Communication.md#aboutresource) 
   	*	3.0.	[Data Validation](./xAPI-Communication.md#validation)     
    	*	3.1.	[Concurrency](./xAPI-Communication.md#concurrency)  
    	*	3.2.	[Error Codes](./xAPI-Communication.md#errorcodes)
    	*	3.3     [Versioning](./xAPI-Communication.md#versioning)  
    *	4.0.	[Authentication](./xAPI-Communication.md#authentication)  
		*	4.1.	[OAuth 1.0 Authentication Scenarios and Methods](./xAPI-Communication.md#authdefs) 
		*	4.2.	[OAuth 1.0 Authorization Scope](./xAPI-Communication.md#oauthscope)
    *	5.0	[Security](./xAPI-Communication.md#security)
	*	[Appendices](./xAPI-Communication.md#append3)  
		*	[Appendix A: Converting Statements to 1.0.0](./xAPI-Communication.md#Appendix3A)  
		*	[Appendix B: Table of All Resources](./xAPI-Communication.md#Appendix3B)  
		*	[Appendix C: Cross Domain Request Example](./xAPI-Communication.md#Appendix3C)  

<a name="partthree"></a>
# Part Three: Data Processing, Validation, and Security 

この第三部では、Experience APIのより技術的な側面について、Learning Record ProviderとLRSの間でStatementsがどのように転送されるかを扱います。JavaScriptを含む様々な技術で、仕様のこの部分を処理する多くのライブラリが利用可能です。したがって、学習記録プロバイダは、仕様のこの部分の詳細を完全に理解する必要はないかもしれません。

<a name="requests"></a>

## <a name="1.0">1.0</a> Requests

xAPI のトラッキングは、Learning Record Provider（クライアント）から LRS（サーバー）への HTTP リクエストで行われます。本仕様はこの通信のいくつかの側面においてガイダンスを提供する。ガイダンスがない場合、xAPI を実装する者は、現在の業界のベストプラクティスを使用することが推奨される。

<a name="httphead"></a>

### <a name="1.1">1.1</a> HEAD Request Implementation

###### <a name="1.1.s1"></a>Description
PUT、POST、GET、DELETE リクエストに対する LRS の動作は、以下の[Resources](#resources)に概説されている。GET リクエストをサポートする全てのリソースは HEAD もサポートする。LRS は HEAD リクエストに対し、実際のドキュメントではなく、HTTP ヘッダを使用したメタ情報のみを返します。

###### <a name="1.1.s2"></a>Rationale

LRS にアクセスするクライアントは、特定のステートメントが存在するかどうかを確認したり、ステートメント、アクティビティプロファイル、エージェントプロファイルリソースなどのドキュメントの更新日を確認する必要があるかもしれません。特に大きなドキュメントの場合、その更新日を確認するためだけにドキュメント全体を取得することは効率的でない。

###### <a name="1.1.s3"></a>LRS Requirements
* <a name="1.1.s3.b1"></a>LRS は HTTP HEAD リクエストに対して、他の同一の HTTP GET リクエストと同様に応答しなければならない (MUST)。
    * <a name="1.1.s3.b1.b1"></a>message-body は省略されなければならない(MUST)。
    * <a name="1.1.s3.b1.b2"></a>LRSのリソースの浪費を避けるため、Content-Lengthヘッダは省略してもよい(MAY)。

<a name="headers"></a> 

### <a name="1.2">1.2</a> Headers

##### <a name="1.2.s1"></a>Header Parameters
xAPIデータ転送で使用されるいくつかのヘッダーパラメータは、[標準的なHTTPヘッダー](http://en.wikipedia.org/wiki/List_of_HTTP_header_fields)です。その他はこの仕様に特有のものである。以下のリクエストヘッダは、学習記録プロバイダがこの仕様で説明するリクエストの種類と状況の一部またはすべてで使用されることが期待されます。

* <a name="1.2.s1.b1"></a>Accept
* <a name="1.2.s1.b2"></a>Accept-Encoding
* <a name="1.2.s1.b3"></a>Accept-Language
* <a name="1.2.s1.b4"></a>Authorization
* <a name="1.2.s1.b5"></a>Content-Type
* <a name="1.2.s1.b6"></a>Content-Length
* <a name="1.2.s1.b7"></a>Content-Transfer-Encoding
* <a name="1.2.s1.b8"></a>If-Match
* <a name="1.2.s1.b9"></a>If-None-Match
* <a name="1.2.s1.b10"></a>X-Experience-API-Version 

以下のレスポンスヘッダがLRSによって使用されることが期待される。繰り返しますが、これら全てが全てのタイプのリクエストや状況に適用されるわけではありません。

* <a name="1.2.s1.b11"></a>Content-Type
* <a name="1.2.s1.b12"></a>Content-Length
* <a name="1.2.s1.b13"></a>Last-Modified
* <a name="1.2.s1.b14"></a>ETag
* <a name="1.2.s1.b15"></a>Status
* <a name="1.2.s1.b16"></a>X-Experience-API-Version
* <a name="1.2.s1.b17"></a>X-Experience-API-Consistent-Through

上記のリストは、すべてを網羅することを意図したものではありません。詳細については、この文書全体の要件を参照してください。

<a name="alt-request-syntax"></a>

### <a name="1.3">1.3</a> Alternate Request Syntax


###### <a name="1.3.s1"></a>Description

xAPI の目的の一つはクロスドメイントラッキングを可能にすることであり、xAPI がブラウザ以外のアプリケーションからのトラッキングを可能にしようとしていても、ブラウザはまだサポートされる必要があります。例えば、Internet Explorer 8と9はCross Origin Resource Sharingを実装しておらず、独自のCross Domain Request APIを使用していますが、"GET" と "POST" のみサポートし、HTTPヘッダの設定を許可しないため、上記のようにxAPIの全てを使用することはできません。

###### <a name="1.3.s2"></a>Details/Requirements

上記の制約により、特定の呼び出しに対して通常の構文が使用できない場合にのみ使用する代替構文について説明します。この代替構文は、クエリ文字列の長さに制限があるため、ステートメントをGETする場合にも使用することができる。

See [Appendix C: Cross Domain Request Example](#Appendix3C) for an example. 

###### <a name="1.3.s3"></a>Requirements

__Method__:  
* <a name="1.3.s3.b1"></a>発行されるすべてのxAPIリクエストはPOSTでなければならない(MUST)。
* <a name="1.3.s3.b2"></a>意図するxAPIメソッドは、クエリ文字列パラメータ "method "の値として含まれなければならない（MUST）。
* <a name="1.3.s3.b3"></a>LRPは、リクエストに他のいかなるクエリ文字列パラメータも含めてはならない（MUST NOT）。

Example: http://example.com/xAPI/statements?method=PUT  

__Content__:  
* <a name="1.3.s3.b4"></a>xAPIコールがコンテンツの送信を含む場合、LRPダはそのコンテンツをURLエンコードし、「content」というフォームパラメータとして含まなければならない(MUST)。 
* <a name="1.3.s3.b5"></a>LRSはこのコンテンツをUTF-8文字列として解釈しなければならない(MUST)。この構文ではバイナリデータの保存はサポートされていない。 

__Headers__:  
* <a name="1.3.s3.b6"></a>LRPは、HTTPヘッダーに現れることが期待される本仕様で要求されるヘッダーパラメータを、同じ名前を持つフォームパラメータとして含めてもよい(MAY)。これは、以下のパラメータに適用される。Authorization、X-Experience-API-Version、Content-Type、Content-Length、If-Match、If-None-Match。Content-Transfer-Encodingには適用されない。
* <a name="1.3.s3.b7"></a>LRS は上に挙げたフォームパラメータをヘッダパラメータとして扱わなければならない(MUST)。
* <a name="1.3.s3.b8"></a>LRPは上記以外のヘッダーパラメータを通常通りHTTPヘッダーに含めなければならない(MUST)。
* <a name="1.3.s3.b9"></a>LRPはこのタイプのリクエストに対しても、'application/x-www-form-urlencoded'という値を持つContent-Typeヘッダー(HTTPヘッダー内)を含めるべきである(SHOULD*)。
request with a value of 'application/x-www-form-urlencoded'. 
* <a name="1.3.s3.b10"></a>Content-Typeフォームパラメータは、コンテンツフォームパラメータ内でコンテンツのコンテンツタイプを指定するべきである(SHOULD*)。
* <a name="1.3.s3.b11"></a>LRPは、このタイプのリクエストに対しても、リクエストのコンテンツ全体の長さを示すContent-Lengthヘッダー（HTTPヘッダー内）を含めるべきです（SHOULD*）。
* <a name="1.3.s3.b12"></a>Content-Lengthフォーム・パラメータは、Contentフォーム・パラメータ内のコンテンツの長さを指定すべきであり、したがってContent-Lengthヘッダーに記載された長さよりも低い数値になる。

__Query string parameters__:  
* <a name="1.3.s3.b13"></a>クエリーストリングパラメーター： "method "以外のすべてのクエリーストリングパラメーターは、代わりに同じ名前のフォームパラメーターとして含まれなければなりません（MUST）。
* <a name="1.3.s3.b14"></a>LRSは "content "または上記のヘッダーパラメータ以外のフォームパラメータをクエリ文字列パラメータとして扱わなければならない(MUST)。

__Attachments__: エンコーディングに関する問題のため，この構文でバイナリデータの添付ファイルを送信することはできないことに注意すること。See [Attachments](./xAPI-Data.md#attachments) 

* <a name="1.3.s3.b15"></a>LRS は上記のシンタックスをサポートしなければならない(MUST)。

クライアントコードがLRSとは異なるスキーム(HTTPまたはHTTPS)でホストされているアプリケーションやブラウザを、学習記録プロバイダがサポートしなければならない場合があるかもしれません。プロキシが必要なのは、IE9以下からのHTTPからHTTPSへのリクエストをサポートしたい場合のみです。最新のブラウザを使えば、プロキシなしで HTTP から HTTPS (または HTTPS から HTTP!) にすることができます。2つの簡単な解決策は、1) LRSへのクライアントコードと同じスキームでプロキシパススルーをセットアップする、2) クライアントコードと同じスキームで中間サーバーサイドLRSをホストしてステートメントをターゲットLRSにルーティングする、かもしれません。

HTTPを使用する実装を使用する決定をする前に、セキュリティリスクを強く考慮すること。

<a name="encoding"></a> 

### <a name="1.4">1.4</a> Encoding

###### <a name="1.4.s1"></a>Requirements
* <a name="1.4.s1.b1"></a>All strings MUST be encoded and interpreted as UTF-8. 

<a name="content-types"></a> 
### <a name="1.5">1.5</a> Content Types
この仕様におけるリクエストとレスポンスは、通常 application/json コンテントタイプを使用する。ただし、例外があります。

* <a name="1.5.b1"></a>ドキュメントは任意のコンテントタイプを持つことができる。
* <a name="1.5.b2"></a>添付ファイルを含むことができるステートメント・リクエストは、multipart/mixedコンテント・タイプを使用する。

<a name="applicationjson"></a> 
#### <a name="1.5.1">1.5.1</a> Application/JSON
この仕様内のリクエストは、通常application/jsonコンテントタイプを使用する。

###### <a name="1.5.1.s1"></a>LRS Requirements
* <a name="1.5.1.s1.b1"></a>Document Type が application/json の PUT または POST を受信する場合、LRS は添付オブジェクトを含まない Statements のバッチを受け入れなければならない(MUST)。
* <a name="1.5.1.s1.b2"></a>ドキュメントタイプが application/json の PUT または POST を受信する場合、LRS は fileUrl が設定されたアタッチメントオブジェクトのみを含むステートメント のバッチを受け入れなければならない(MUST)。

<a name="multipartmixed"></a> 
#### <a name="1.5.2">1.5.2</a> Multipart/Mixed

`multipart/mixed`コンテンツタイプは、Attachmentsを含む可能性があるリクエストに使用される。これは、すべての「multipart/mixed」リクエストが必ずAttachmentsを含むということを意味しない。

##### <a name="1.5.2.s1"></a>Procedure For The Exchange Of Attachments

* <a name="1.5.2.s1.b1"></a>0個以上の添付ファイルを含むステートメントリクエストは、以下に記述されるように解釈される。

* <a name="1.5.2.s1.b2"></a>ステートメントは、Content-Type として multipart/mixed を使用して送信される。すべての添付ファイルは、そのような送信の最後に置かれる。

* <a name="1.5.2.s1.b3"></a>LRS は最初の部分の情報に基づいて、ステートメントを受け入れるか拒否するかを決定する。

* <a name="1.5.2.s1.b4"></a>要求を受け入れる場合、LRSは生データのSHA-2とヘッダーで宣言されたSHA-2を比較することで、添付ファイルの生データを添付ファイルヘッダにマッチングさせることができる。それ以外の方法でそれを行ってはならない[MUST]。

###### <a name="1.5.2.s2"></a>Requirements for Attachment Statement Batches

Statementバッチ、Statement結果、または添付ファイルを含む単一のStatementを送信するリクエストは、以下の基準のいずれかを満たさなければなりません。

* <a name="1.5.2.s2.b1"></a>タイプはapplication/jsonでなければならず、各アタッチメントのfileUrlを含まなければならない（ただし、"attachments "フィルタが`false`の場合はStatement resultsを除く）。
* <a name="1.5.2.s2.b2"></a>それは、[RFC 2046](https://www.ietf.org/rfc/rfc2046.txt)の「multipart/mixed」の定義に準拠しなければならない(MUST)し、また:
    * <a name="1.5.2.s2.b2.b1"></a>マルチパートドキュメントの最初の部分は、Statementそのものを、`application/json`タイプで含まなければならない(MUST)。
    * <a name="1.5.2.s2.b2.b2"></a>マルチパート文書の最初のパートは、Application/jsonタイプでStatements自体を含まなければならない(MUST)。追加の各パートは、Attachmentの生データを含み、Statementの論理パートを形成する。この機能は、Statement Resource に対して PUT または POST リクエストを発行する際に利用可能である。
    * <a name="1.5.2.s2.b2.b3"></a>最初の(Statement)パートの後の各パートのヘッダーにX-Experience-API-Hashパラメータを含めなければならない(MUST)。
    * <a name="1.5.2.s2.b2.b4"></a>最初の（Statements）部分の後の各部分のヘッダーに、値がbinaryであるContent-Transfer-Encodingパラメータを含めなければならない（MUST）。
    * <a name="1.5.2.s2.b2.b5"></a>同じ添付ファイルが、一緒に送信される複数のStatementsで使用される場合、添付ファイルのデータ のコピーを1つだけ含めるべきである(SHOULD)。
    * <a name="1.5.2.s2.b2.b6"></a>各パートのヘッダーにContent-Typeパラメータを含めるべきである(SHOULD)。最初のパート(Statementを含む)では、これは`application/json`でなければならない(MUST)。
   	* <a name="1.5.2.s2.b2.b7"></a>パラメータがアタッチメントオブジェクト内に対応するプロパティを持ち（上記の表で概説）、パラメータとプロパティの両方が与えられたアタッチメントに対して指定される場合、これらのパラメータとプロパティの値は一致しなければならない（MUST）。

###### <a name="1.5.2.s3"></a>LRS Requirements

* <a name="1.5.2.s3.b1"></a>LRS はクライアントから要求された場合、上記の送信フォーマットに添付ファイルを含めなけれ ばならない(see [Statement Resource](#stmtres)).
* <a name="1.5.2.s3.b2"></a>LRSは添付ファイルを要求することなく、他のLRSからステートメントを取得してはならない。
* <a name="1.5.2.s3.b3"></a>LRS は他の LRS にステートメントをプッシュする際に、受信した添付ファイルを含めなければ ならない。 を含むことなく、ステートメントを他の LRS にプッシュしてはならない（もしあれば）。
* <a name="1.5.2.s3.b4"></a>ドキュメントタイプが multipart/mixed である PUT または POST を受信する場合、LRS は前述の送信フォー マットで添付ファイルを含むステートメントのバッチを受け入れなければならない(MUST)。
* <a name="1.5.2.s3.b5"></a>ドキュメントタイプが multipart/mixed の PUT または POST を受信する場合、LRS は fileUrl を含まず、受信した Attachment パートにハッシュに基づいて一致しない Attachment を有する Statements のバッチを拒否しなければならない。
* <a name="1.5.2.s3.b6"></a>ドキュメントタイプが multipart/mixed の PUT または POST を受信する場合、LRS は添付ファイル部分の Content-Transfer-Encoding を binary と仮定するべきである(SHOULD)。
* <a name="1.5.2.s3.b7"></a>LRSは、LRSが許可するように設定されているよりも大きなステートメントの(バッチ)を拒否してもよい。
* <a name="1.5.2.s3.b8"></a>ドキュメントタイプが multipart/mixed である PUT または POST を受信するとき、LRS は添付オブジェクトを含まないステートメントの バッチを受け入れるべきである(SHOULD*)。
* <a name="1.5.2.s3.b9"></a>ドキュメントタイプが multipart/mixed の PUT または POST を受信する場合、LRS は fileUrl が入力された添付オ ブジェクトのみを含むステートメントのバッチを受理すべきである(SHOULD*)。

__Note:__ "mime/multipart "形式を使用するStatementバッチが添付ファイルを含むことは要求されていない。

###### <a name="1.5.2.s4"></a>Learning Record Provider Requirements

* <a name="1.5.2.s4.b1"></a>A Learning Record Providerは、上記のようにStatementsにAttachmentsを送信してもよい（MAY）。
* <a name="1.5.2.s4.b2"></a>A Learning Record Providerは、POST を使用する場合、一部または全部が添付ファイルを持つ複数のステートメントを送信してもよい（MAY）。
* <a name="1.5.2.s4.b3"></a>A Learning Record Providerは、"multipart/mixed "フォーマットに基づくすべての要件を無視して、すべての添付ファイルオブジェクトが fileUrl を持つ application/json タイプのバッチを送信してもよい(MAY)。
* <a name="1.5.2.s4.b4"></a>A Learning Record Providerは、SHA-256、SHA-384、またはSHA-512を使用して、"sha2 "プロパティを入力する必要があります(SHOULD)。

###### <a name="1.5.2.s5"></a>File URL
ファイルURLは、添付ファイルを受信することができる場所を提供することを意図している。しかし、添付ファイルの所有者は、その場所で添付ファイルのデータを無期限に利用できるようにすること、またはセキュリティ上の制限なしに添付ファイルを一般に公開することを要求されることはない。添付ファイルのホスティングを決定する際、"fileUrl "プロパティを使用してステートメントを作成する者は、特に 添付ファイルコンテンツがステートメントに含まれていない場合、ステートメントの最終受信者のニーズを考慮することが推奨さ れる。

* <a name="1.5.2.s5.b1"></a>添付ファイルのデータは、fileUrl で示される URL で取得可能であるべきである（SHOULD）。
* <a name="1.5.2.s5.b2"></a>添付ファイルの所有者は、このIRLでの添付ファイルデータの提供をいつでも中止することができる。
* <a name="1.5.2.s5.b3"></a>このIRLで添付ファイルデータにアクセスしようとする者には、セキュリティ上の制限が適用されてもよい。


添付ファイルが利用可能になる期間や、ホストされた添付ファイルに適用されるセキュリティ制限は、本仕様の範囲外である。

###### <a name="1.5.2.s6"></a>Example

以下は、添付ファイル付きの非常に単純なステートメントの例である。以下の点に注意してください。

* <a name="1.5.2.s6.b1"></a>サンプルの境界線は、有効な文字クラスを示すために選択されています。
選択された境界線は、どの部分にも現れません。
* <a name="1.5.2.s6.b2"></a>選択された境界線は、どの部分にも現れません。
* <a name="1.5.2.s6.b3"></a>読みやすくするために、サンプルの添付ファイルは「text/plain」タイプになっています。仮に「image/jpeg」のようなバイナリタイプであったとしても、エンコーディングは行われず、生のオクテットが含まれることになります。
* <a name="1.5.2.s6.b4"></a>RFC2046によると、境界は`<CRLF>`の後に--が続き、その後にヘッダーで宣言された境界文字列が続きます。

__Note:__ これらのメッセージを構築または解析する際には、```<CRLF>```を忘れないようにしてください。

Headers:

``` 
Content-Type: multipart/mixed; boundary="abcABC0123'()+_,-./:=?"
X-Experience-API-Version:1.0.0
```
Content:
```

--abcABC0123'()+_,-./:=?
Content-Type:application/json

{
    "actor": {
        "mbox": "mailto:sample.agent@example.com",
        "name": "Sample Agent",
        "objectType": "Agent"
    },
    "verb": {
        "id": "http://adlnet.gov/expapi/verbs/answered",
        "display": {
            "en-US": "answered"
        }
    },
    "object": {
        "id": "http://www.example.com/tincan/activities/multipart",
        "objectType": "Activity",
        "definition": {
            "name": {
                "en-US": "Multi Part Activity"
            },
            "description": {
                "en-US": "Multi Part Activity Description"
            }
        }
    },
    "attachments": [
        {
            "usageType": "http://example.com/attachment-usage/test",
            "display": { "en-US": "A test attachment" },
            "description": { "en-US": "A test attachment (description)" },
            "contentType": "text/plain; charset=ascii",
            "length": 27,
            "sha2": "495395e777cd98da653df9615d09c0fd6bb2f8d4788394cd53c56a3bfdcd848a"
        }
    ]
}
--abcABC0123'()+_,-./:=?
Content-Type:text/plain
Content-Transfer-Encoding:binary
X-Experience-API-Hash:495395e777cd98da653df9615d09c0fd6bb2f8d4788394cd53c56a3bfdcd848a

here is a simple attachment
--abcABC0123'()+_,-./:=?--
```

<a name="datatransfer"></a> <a name="resources"></a>
## <a name="2.0">2.0</a> Resources

LRS は RESTful HTTP メソッドを介して、このセクションで概要を説明するリソースと対話します。ステートメントリソースは、それ自体で学習記録を追跡するために使用することができます。他のリソースは追加機能を提供します。

LRSはこのセクションで説明したリソースを全てサポートする。LRSでないツールは、このセクションで説明されているリソースとメソッドの1つ以上のLRS要件に従うことを選択することも可能である。例えば、あるツールはLRSから転送される受信ステートメントを受信する目的でPOSTステートメントを実装するかもしれない。このようなシステムは、LRSまたは "部分的LRS "とはみなされない。

__Note:__ 本仕様で示されるxAPIリソースが配置されるすべてのエンドポイント例において、`http://example.com/xAPI/` 
はLRSのベースエンドポイントの例である。これ以降の他の全てのIRI構文は、使用される特定のリソースを表している。エンドポイントの完全なリストは、[Appendix B: Table of All Resources](#Appendix3B)全リソースの表に含まれている。

###### <a name="2.0.s1"></a>Requirements

* <a name="2.0.s1.b1"></a>LRS はこのセクションで説明されるすべてのリソースをサポートしなければならない（MUST）。
* <a name="2.0.s1.b2"></a>LRS が OAuth 1.0 を実装している場合、LRS は[OAuth Authorization Scope](#oauthscope)に記述されている全ての OAuth リソースもサポートしなければならない。 
* <a name="2.0.s1.b3"></a>LRS は本仕様に記載されていない追加リソースをサポートしてもよい（MAY）
* <a name="2.0.s1.b4"></a>この仕様の過去、現在、未来のバージョンでは、`extensions/` で始まるパスセグメントを持つエンドポイントは定義されていませんし、今後も定義されないでしょう。この仕様で定義されていない追加のリソースをサポートする LRS は、`extensions/` で始まるパスセグメントを持つエンドポイントを定義するべきである(SHOULD)。

<a name="stmtres"></a> 

#### <a name="2.1">2.1</a> Statement Resource

###### <a name="2.1.s1"></a>Description

The basic communication mechanism of the Experience API.
Experience API の基本的な通信機構です。

<a name="stmtresput"></a>

#### <a name="2.1.1">2.1.1</a> PUT Statements

###### <a name="2.1.1.s1"></a>Details

Example endpoint: `http://example.com/xAPI/statements`

指定されたIDのStatementを1つ格納します。POSTも単一のStatementを格納するために使用することができます。

**Content:** The Statement object to be stored. 

**Returns:** `204 No Content`  

<table>
	<tr><th>Parameter</th><th>Type</th><th>Default</th><th>Description</th><th>Required</th></tr>
	<tr id="2.1.1.s1.table1.row1"><td>statementId</td><td>String</td><td> 
	<td>Id of Statement to record</td></td><td>Required</td></tr>
</table>

###### <a name="2.1.1.s2"></a>LRS Requirements

* <a name="2.1.1.s2.b1"></a>LRSは、保存されたStatementが検索可能になる前に応答してもよい(MAY)。

* <a name="2.1.1.s2.b2"></a>LRSは、すでにステートメントを持っているstatementIdのステートメントを受信したことに基づいて、そのステートにいかなる修正も加えてはならない(MUST NOT)。`409 Conflict`または`204 No Content`応答しようとも、ステートメントまたは他のオブジェクトを修正してはならない(MUST NOT)。

* <a name="2.1.1.s2.b3"></a>LRSが既に持っているステートメントIDを持つステートメントを受信した場合、受信したステートメントが既存のものと一致することを確認すべきであり、一致しない場合は`409 Conflict`を返さなければならない（SHOULD）。[Statement comparison requirements](./xAPI-Data.md#statement-comparison-requirements)参照。

* <a name="2.1.1.s2.b4"></a>LRSが同じidを持つ2つ以上のStatementを含むStatementのバッチを受信した場合、バッチを拒否し、`400 Bad Request`を返すべきである

###### <a name="2.1.1.s3"></a>Learning Record Provider Requirements

* <a name="2.1.1.s3.b1"></a>学習記録プロバイダは、PUTを使用する代わりに、ステートメント「id」プロパティを含むステートメントをPOSTすべきです（SHOULD）。
* <a name="2.1.1.s3.b2"></a>ステートメントをPUTする場合、ステートメントの "id "プロパティを使用すべきです。
* <a name="2.1.1.s3.b3"></a>ステートメントの "id "プロパティは、リクエストの "statementId "パラメータと一致しなければならない（MUST）。

<a name="stmtrespost"></a>

#### <a name="2.1.2">2.1.2</a> POST Statements

###### <a name="2.1.2.s1"></a>Details

エンドポイント例： `http://example.com/xAPI/statements`

ステートメント、またはステートメントのセットを保存します。

**Content:** Statementの配列、または格納される1つのStatement。

**Returns:** `200 OK`, 200 OK、格納されたステートメントと同じ順序のステートメントID(UUID)の配列。

###### <a name="2.1.2.s2"></a>Requirements

* <a name="2.1.2.s2.b1"></a>MAY:LRSは、保存されたステートメントが検索可能になる前に応答してもよい。
* <a name="2.1.2.s2.b2"></a>GETステートメントは、クエリ文字列には制限があるため、必要に応じてPOSTとフォームパラメータを使用して呼び出すことができます（MAY）。See [Alternate Request Syntax](#alt-request-syntax) for more details.
* <a name="2.1.2.s2.b3"></a>LRSは、渡されたパラメータに基づいてStatementを追加したり、Statementを一覧表示するためにPOSTを区別しなければならない(MUST)。See [Alternate Request Syntax](#alt-request-syntax) for more details.
* <a name="2.1.2.s2.b4"></a>LRSは、すでにステートメントを持っているIDのステートメントを受信したことに基づいて、そのステートにいかなる修正も加えてはならない(MUST NOT)。`409 Conflict`または`204 No Content`で応答しても、ステートメントまたは他のオブジェクトを修正してはならない(MUST NOT)。
* <a name="2.1.2.s2.b5"></a>LRSが既に持っているidを持つステートメントを受信した場合、受信したステートメントが既存のものと一致することを確認すべきであり、一致しない場合は`409 Conflict`を返すべきである（SHOULD）。
See [Statement comparison requirements](./xAPI-Data.md#statement-comparison-requirements).
* <a name="2.1.2.s2.b6"></a>LRSが同じidを持つ2つ以上のStatementを含むStatementのバッチを受信した場合、バッチを拒否し、`400 Bad Request`を返すべきである(SHOULD*)。

<a name="stmtresget"></a>

#### <a name="2.1.3">2.1.3</a> GET Statements

###### <a name="2.1.3.s1"></a>Details

Example endpoint: `http://example.com/xAPI/statements`

このメソッドは、単一のステートメントまたは複数のステートメントをフェッチするために呼び出されます。statementId または voidedStatementId パラメータが指定されている場合は、単一のステートメントが返されます。

それ以外の場合は、以下を返します： [StatementResult](./xAPI-Data.md#retrieval)オブジェクト。"stored "時間に基づく逆時系列順のStatementのリストで、権限とリストの最大長に従います。追加の結果が利用可能な場合、それらを取得するための IRL が StatementResult Object に含まれます。

**Content:** None.

**Returns:** `200 OK`, Statement or [Statement Result](./xAPI-Data.md#retrieval)

<table>
	<tr><th>Parameter</th><th>Type</th><th>Default</th><th>Description</th><th>Required</th></tr>
	<tr id="2.1.3.s1.table1.row1">
		<td>statementId</td>
		<td>String</td>
		<td> </td>
		<td>Id of Statement to fetch</td>
		<td>Optional</td>
	</tr>
	<tr id="2.1.3.s1.table1.row2">
		<td>voidedStatementId</td>
		<td>String</td>
		<td> </td>
		<td>Id of voided Statement to fetch. see <a href="./xAPI-Data.md#voided">Voided
		Statements</a></td>
		<td>Optional</td>
	</tr>
	<tr id="2.1.3.s1.table1.row3">
		<td>agent</td>
		<td>Agent or Identified Group Object (JSON)</td>
		<td> </td>
		<td>Filter,指定されたエージェントまたはグループがステートメントのアクターまたはオブジェクトであるステートメントのみを返します。
			<ul>
				<li> 
					エージェントまたは識別されたグループは、比較された各オブジェクトで同じ逆機能識別子が使用され、それらの逆機能識別子が同じ値を持つ場合に等しくなります。
				</li><li>
					このフィルタでは、上記のように逆機能識別子に基づいて指定されたエージェントに一致するメンバーを持つグループは、一致すると見なされます。
				</li>
			</ul>
			<br><br>See <a href="./xAPI-Data.md#actor">agent/group</a> Object definition
			for details.
		</td>
		<td>Optional</td>
	</tr>
	<tr id="2.1.3.s1.table1.row4">
		<td>verb</td>
		<td>Verb id (IRI)</td>
		<td> </td>
		<td>フィルタリングを行い、指定したVerb idに一致するStatementのみを返す。</td>
		<td>Optional</td>
	</tr>
	<tr id="2.1.3.s1.table1.row5">
		<td>activity</td>
		<td>Activity id (IRI)</td>
		<td> </td>
		<td>
			フィルタリングにより、ステートメントのオブジェクトが指定されたIDを持つアクティビティであるステートメントのみを返します。
		</td>
		<td>Optional</td>
	</tr>
	<tr id="2.1.3.s1.table1.row6">
		<td>registration</td>
		<td>UUID</td>
		<td> </td>
		<td>
			指定された登録IDに一致するステートメントのみを返すフィルタです。1つのアクターに1つのアクティビティが割り当てられた場合、一意の登録が使用されることがよくありますが、これを仮定することはできませんのでご注意ください。特定のアクターやアクティビティのステートメントだけが必要な場合は、それらのパラメータも指定する必要があります。
		</td>
		<td>Optional</td>
	</tr>
	<tr id="2.1.3.s1.table1.row7">
	<td>related_activities</td>
		<td>Boolean</td>
		<td>false</td>
		<td>
			Activity フィルタを広く適用します。オブジェクト、コンテキストのアクティビティ、または含まれるSubStatementのこれらのプロパティのいずれかがActivityパラメータと一致するStatementを、パラメータの通常の動作の代わりに含めます。マッチングは、"activity "パラメータと同じように定義されます。
		</td>
		<td>Optional</td>
	</tr>
	<tr id="2.1.3.s1.table1.row8">
		<td>related_agents</td>
		<td>Boolean</td>
		<td>false</td>
		<td>
			Agent フィルタを広く適用します。SubStatementに含まれるActor、Object、Authority、Instructor、Team、またはこれらのプロパティのいずれかがAgentパラメータと一致するStatementを、パラメータの通常の動作の代わりに含めることができます。マッチングは、"agent "パラメータと同じように定義されます。
		</td>
		<td>Optional</td>
	</tr>
	<tr id="2.1.3.s1.table1.row9">
		<td>since</td>
		<td>Timestamp</td>
		<td> </td>
		<td>指定されたタイムスタンプ（排他的）以降に保存されたステートメントのみが返されます。</td>
		<td>Optional</td>
	</tr>
	<tr id="2.1.3.s1.table1.row10">
		<td>until</td>
		<td>Timestamp</td>
		<td> </td>
		<td>指定されたタイムスタンプ以前に保存されたステートメントのみが返されます。</td>
		<td>Optional</td>
	</tr>
	<tr id="2.1.3.s1.table1.row11">
		<td>limit</td>
		<td>Nonnegative Integer</td>
		<td>0</td>
		<td>
			返すステートメントの最大数。0 は、サーバーが許可する最大数を返すことを示します。
		</td>
		<td>Optional</td>
	</tr>
	<tr id="2.1.3.s1.table1.row12">
		<td>format</td>
		<td>String: (<code>ids</code>, <code>exact</code>, or <code>canonical</code>)</td>
		<td>exact</td>
		<td>
			<code>ids</code>がある場合は、エージェント、アクティビティ、動詞、グループオブジェクトに、それらを識別するために必要な最小限の情報のみを含める。匿名グループの場合は、各メンバーを識別するために必要な最小限の情報を含めることを意味します。
			<br/><br/>
			<code>exact</code>な場合は、エージェント、アクティビティ、動詞、およびグループオブジェクトを、ステートメントを受信したときと同じように入力して返却します。ステートメントをインポートする目的でステートメントを要求するLRSは、<a href="./xAPI-Data.md#statement-immutability-and-exceptions">Statement Immutability</a>を維持するため、"exact "の形式を使用する。
			<br/><br/>
			<code>canonical</code>の場合、<a href="#queryLangFiltering">以下に定義されるlanguage filtering process</a>を適用した後、LRSが決定したアクティビティオブジェクトの正規の定義と動詞の表示で、アクティビティオブジェクトと動詞を入力し、元のエージェントオブジェクトとグループオブジェクトを「正確」モードで返します。
		</td>
		<td>Optional</td>
	</tr>
	<tr id="2.1.3.s1.table1.row13">
		<td>attachments</td><td>Boolean</td><td>false</td>
		<td><code>true</code>の場合、LRSはマルチパート応答形式を使用し、前述のようにすべての添付ファイルを含めます。<code>false</code>,の場合、LRS は Content-Type application/json で所定の応答を送信し、添付データを送信しません。</td>
		<td>Optional</td>
	</tr>
	<tr id="2.1.3.s1.table1.row14">
		<td>ascending</td>
		<td>Boolean</td>
		<td>false</td>
		<td><code>true</code>の場合、保存された時間の昇順で結果を返す</td>
		<td>Optional</td>
	</tr>
</table>

__Note:__ The values of Boolean parameters are represented as `true` or `false` as in JSON.
###### <a name="2.1.3.s2"></a>Requirements

* <a name="2.1.3.s2.b1"></a>LRS は、statementId と voidedStatementId の両方のパラメータを含むこのリソースへのリクエストを `400 Bad Request` エラーで拒否しなければならない。(MUST)

* <a name="2.1.3.s2.b2"></a>LRSは、statementIdまたはvoidedStatementIdパラメータを含み、かつ「attachments」または「format」以外のパラメータを含むこのリソースへのリクエストを、`400 Bad Request`エラーで拒否しなければならない。(MUST)

* <a name="2.1.3.s2.b3"></a>LRSは、使用されたクレデンシャルに関連するパーミッションに基づいて、追加のクエリフィルタ基準を適用してもよい（MAY）。

* <a name="2.1.3.s2.b4"></a>クエリフィルタ基準に一致するStatementsが見つからない場合でも、LRSは`200 OK`と[StatementResult](./xAPI-Data.md#retrieval)Objectを返さなければならない(MUST)。この場合、"states "プロパティには空の配列が含まれる。

* <a name="2.1.3.s2.b5"></a>LRS は、Statement Resource リクエストに対するすべてのレスポンスに、[ISO 8601 combined date and time](https://en.wikipedia.org/wiki/ISO_8601#Combined_date_and_time_representations)  の日付と時刻を組み合わせた形式のヘッダー "X-Experience-API-Consistent-Through" を含めなければならない（このヘッダーの値は、その時間以前に "stored" プロパティを持つ、または持つ予定のすべての Statement が、検索に使用できることが妥当な確度でわかっているタイムスタンプである）。この時間は、Statementsが検索に利用できるようになるのを遅らせる原因となる、過度の負荷などの一時的な状態を考慮に入れるべきである（SHOULD）。最近受信したStatementがない場合でも、これは最近のタイムスタンプであることが期待される。
The LRS MUST include the header "X-Experience-API-Consistent-Through", in 

* <a name="2.1.3.s2.b6"></a>GETステートメントの "attachment "プロパティが使用され、`true`に設定されている場合、LRSはマルチパート応答形式を使用し、[Part Two](./xAPI-Data.md#attachments)に記載されているように全ての添付ファイルを含めなければならない(MUST)。

* <a name="2.1.3.s2.b7"></a>GETステートメントのattachmentプロパティが使用され、`false`に設定された場合、LRSはAttachmentの生データを含んではならず、`application/jsonを報告しなければならない(MUST)。

* <a name="2.1.3.s2.b8"></a>LRSはステートメントの "stored "タイムスタンプと一致する "Last-Modified "ヘッダを含めるべきである(SHOULD*)。

<a name="queryStatementRef"></a>

###### <a name="2.1.3.s3"></a>StatementRefのフィルタ条件

このセクションでは、他のステートメントを対象とするステートメントが、元のクエリのフィルタ・パラメータと一致しない場合でも、クエリのフィルタ条件を満たすと見なされる場合があるルールの概要を説明します。これらのルールは、「statementId」または「voidedStatementId」クエリパラメータを使用して1つのStatementを取得する場合には適用**されません**。

'Targeting Statements'とは、あるステートメント（対象ステートメント）が、ステートメントのオブジェクトとしてのステートメント参照として、別のステートメント（対象ステートメント）のステートメントIDを含むことを意味します。

時間またはシーケンスに基づかないフィルタパラメータ（つまり、「since」、「until」、「limit」以外）の場合、別のステートメントをターゲットとするステートメントは（ステートメントのオブジェクトとしてStatementRefを使用することにより）、ターゲットとなるステートメントがフィルタ条件を満たしていればフィルタ条件を満たすことになります。

時間およびシーケンスに基づくパラメータは、この方法でStatementRefを作成するStatementに適用されなければならない（MUST）。このルールは再帰的に適用され、「ステートメントa」は、aがbをターゲットとし、それがcをターゲットとし、「ステートメントc」に対して上述のフィルタ条件が一致する場合に一致することになる。

例えば、「Ben passed explosives training」というStatementと、それに続くStatementを考えてみましょう： 「Andrewは<StatementRef to original Statement>を確認した」とする。フォローアップ・ステートメントには「Ben」や「explosives training」の記述はありませんが、アクター・フィルターが「Ben」、アクティビティ・フィルターが「explosives training」のステートメントをフェッチすると、フェッチした時間またはシーケンスに該当する限り、両方のステートメントがマッチして返されます。

__Note:__ Context内の "Statement "プロパティの値として使用されるStatementRefは、Statementのフィルタリング方法には影響しません。

<a name="queryLangFiltering"></a>

###### <a name="2.1.3.s4"></a>Language Filtering Requirements for Canonical Format Statements(カノニカルフォーマットステートメントの言語フィルタリング要件)

* <a name="2.1.3.s4.b1"></a>アクティビティオブジェクトは、"name"、"description"、様々なインタラクションコンポーネント内にLanguage Map Objectsを含む。LRSは、これらのマップのそれぞれにおいて、1つの言語のみを返さなければならない（MUST）。

* <a name="2.1.3.s4.b2"></a>LRSは、言語マップを含むオブジェクトを識別するあらゆるIRIに対して、言語マップの正規版を維持してもよい（MAY）。これにはVerbの "display "プロパティに格納されている言語マップや、拡張機能内で使用される言語マップも含まれる可能性がある。

* <a name="2.1.3.s4.b3"></a>LRSが言語マップの正規版を保持している場合、Statementsを取得するためにcanonicalフォーマットが使用されたときに、この正規版の言語マップを返すべきである（SHOULD*）。

* <a name="2.1.3.s4.b4"></a>LRSは、カノニカルマップを返す各言語マップの中で、1つの言語のみを返すべきである(SHOULD*)。 

* <a name="2.1.3.s4.b5"></a>最も関連性の高い言語を選択するために、LRSは[RFC 2616](http://www.w3.org/Protocols/rfc2616/rfc2616-sec14.html)(HTTP 1.1)に記述されている「Accept-Language」ヘッダーを適用しなければならないが、この論理はリソース（ステートメントのリスト）全体ではなく、どの言語項目を含めるかを選択するために各言語マップに対して個別に適用しなければならない（MUST）。

<a name="voidedStatements"></a>

##### <a name="2.1.4">2.1.4</a> Voided Statements
[Part Two](./xAPI-Data.md#voided) では、ステートメントを無効化するためのプロセスについて説明する。本節では、無効化されたステートメントがLRSに照会された際にどのように処理されるかを説明する。

クライアントは、無効化されたステートメントのターゲットによって、その存在とステートメントIDを特定することができます。デバッグツールは別として、多くの学習記録コンシューマは無効化されたステートメントをユーザに表示したくないと考え、アクティビティストリームや他のレポートの一部として表示しません。

###### <a name="2.1.4.s1"></a>Requirements

* <a name="2.1.4.s1.b1"></a>LRS は、voidedStatementId によって要求された Statement を除き、無効化された Statement を返してはならない(MUST)。[StatementRefのフィルタ条件に関するセクション](#queryStatementRef)で説明したプロセスは、この要求に対する例外ではない。無効化されたStatementを取得するプロセスは、voidedStatementIdによってそれぞれを個別に要求することである。

* <a name="2.1.4.s1.b2"></a>LRSは、[StatementRefのフィルタ条件のセクション](#queryStatementRef)で説明したプロセスと条件に従って、無効化されたStatementを対象としたStatementを返さなければならない。これには、無効にできない無効化ステートメントも含まれる。

<a name="doctransfer"></a>

### <a name="2.2">2.2</a> Document Resources 

##### <a name="2.2.s1"></a>Description
Experience APIは、Learning Record Providerが任意のデータをドキュメントの形で保存するための機能を提供するもので、アクティビティ、エージェント、またはその両方の組み合わせに関連している可能性があります。

##### <a name="2.2.s2"></a>Details
以下の表は一般的なプロパティを示しており、この仕様の他の多くの表のようなJSONオブジェクトではないことに注意してください。id は IRL に格納され、"updated" は HTTP ヘッダー情報、"contents" は (Object とは対照的に) HTTP ドキュメントそのものです。
<table>
	<tr><th>Property</th><th>Type</th><th>Description</th></tr>
	<tr id="2.2.s2.table1.row1"><td>id</td><td>String</td><td>Set by Learning Record Provider, unique within the scope 
	of the Agent or Activity.</td></tr>
	<tr id="2.2.s2.table1.row2"><td>updated</td><td>Timestamp</td><td>When the document was most recently modified.</td></tr>
	<tr id="2.2.s2.table1.row3"><td>contents</td><td>Arbitrary binary data</td><td>The contents of the document</td></tr>
</table>

The three Document Resources provide [document](./xAPI-Data.md#documents) storage.  The details of each resource are found in 
the following sections, and the information in this section applies to all three resources.

###### <a name="2.2.s3"></a>Details

<table>
	<tr>
		<th>Resource</th>
		<th>Method</th>
		<th>Endpoint</th>
		<th>Example</th>
	</tr>
	<tr id="2.2.s3.table1.row1">
		<td>State Resource</td>
		<td>POST</td>
		<td>activities/state</td>
		<td>http://example.com/xAPI/activities/state</td>
	</tr>
	<tr id="2.2.s3.table1.row2">
		<td>Activity Profile Resource</td>
		<td>POST</td>
		<td>activities/profile</td>
		<td>http://example.com/xAPI/activities/profile</td>
	</tr>
	<tr id="2.2.s3.table1.row3">
		<td>Agent Profile Resource</td>
		<td>POST</td>
		<td>agents/profile</td>
		<td>http://example.com/xAPI/agents/profile</td>
	</tr>
</table>

###### <a name="2.2.s4"></a>Requirements

* <a name="2.2.s4.b1"></a>A Learning Record Provider MAY send documents to any of the Document Resources for Activities and 
Agents that the LRS does not have prior knowledge of. 

* <a name="2.2.s4.b2"></a>The LRS MUST NOT reject documents on the basis of not having prior knowledge of the Activity and/or Agent.

##### <a name="2.2.s5"></a>Last Modified
The "Last Modified" header is set by the LRS when returning single or multiple documents in response to a GET request. 

###### <a name="2.2.s6"></a>Requirements
* <a name="2.2.s6.b1"></a>When returning a single document, the LRS SHOULD* include a "Last-Modified" header indicating when
the document was last modified. 
* <a name="2.2.s6.b2"></a>When returning multiple documents, the LRS SHOULD* include a "Last-Modified" header indicating when
the most recently modified document was last modified. 

###### <a name="2.2.s7"></a>JSON Procedure with Requirements

If a Learning Record Provider stores variables as JSON Objects in a document with content type `application/json`, 
they can manipulate them as sets of variables using POST.

The following process walks through that process and the process requirements.  
For example, a document contains: 

```
{
	"x" : "foo",
	"y" : "bar"
}
```  
When an LRS receives a POST request with content type `application/json` for an existing document also of
content type `application/json`, it MUST merge the posted document with the existing document. 
In this context, merge is defined as:
* <a name="2.2.s7.b1"></a>de-serialize the Objects represented by each document.
* <a name="2.2.s7.b2"></a>for each property directly defined on the Object being posted, set the corresponding
property on the existing Object equal to the value from the posted Object.    
* <a name="2.2.s7.b3"></a>store any valid json serialization of the existing Object as the document referenced in the request.

Note that only top-level properties are merged, even if a top-level property is an Object. The entire contents of each 
original property are replaced with the entire contents of each new property.

For example, this document is POSTed with the same id as the existing document above:

```
{
	"x" : "bash",
	"z" : "faz"
}
```  
the resulting document stored in the LRS is:
```
{
	"x" : "bash",
	"y" : "bar",
	"z" : "faz"
}
```

###### <a name="2.2.s8"></a>Requirements

* <a name="2.2.s8.b1"></a>If the document being posted or any existing document does not have a Content-Type
of `application/json`, or if either document cannot be parsed as a JSON Object, the LRS MUST
respond with HTTP status code `400 Bad Request`, and MUST NOT update the target document
as a result of the request.

* <a name="2.2.s8.b2"></a>If the merge is successful, the LRS MUST respond with HTTP status code `204 No Content`.

* <a name="2.2.s8.b3"></a>If a Learning Record Provider needs to delete a property, it SHOULD use a PUT request to replace 
the whole document as described below. 

<a name="stateres"></a> 

### <a name="2.3">2.3</a> State Resource

##### <a name="2.3.s1"></a>Description

Generally, this is a scratch area for Learning Record Providers that do not have their own internal storage, 
or need to persist state across devices. 

##### <a name="2.3.s2"></a>Details

The semantics of the call are driven by the "stateId" parameter. If it is included, the GET and DELETE methods will 
act upon a single defined state document identified by "stateId". Otherwise, GET will return the available ids, 
and DELETE will delete all state in the context given through the other parameters. This resource has
[Concurrency](#concurrency) controls associated with it.

###### <a name="2.3.s3"></a>Single Document (PUT | POST | GET | DELETE)

Example endpoint: http://example.com/xAPI/activities/state

Stores, changes, fetches, or deletes the document specified by the given "stateId" that 
exists in the context of the specified Activity, Agent, and registration (if specified).  

**Content (PUT | POST):** The document to be stored or updated.  
**Content (GET | DELETE):** None.  

**Returns (PUT | POST | DELETE):** `204 No Content`  
**Returns (GET):** `200 OK`, the State document 
<table>
	<tr><th>Parameter</th><th>Type</th><th>Description</th><th>Required</th></tr>
	<tr id="2.3.s3.table1.row1">
		<td>activityId</td>
		<td>Activity id (IRI)</td>
		<td>The Activity id associated with this state.</td>
		<td>Required</td>
	</tr>
	<tr id="2.3.s3.table1.row2">
		<td>agent</td>
		<td>Agent Object (JSON)</td>
		<td>The Agent associated with this state.</td>
		<td>Required</td>
	</tr>
	<tr id="2.3.s3.table1.row3">
		<td>registration</td>
		<td>UUID</td>
		<td>The registration associated with this state.</td>
		<td>Optional</td>
	</tr>
	<tr id="2.3.s3.table1.row4">
		<td>stateId</td>
		<td>String</td>
		<td>The id for this state, within the given context.</td>
		<td>Required</td>
	</tr>
</table>

###### <a name="2.3.s4"></a>Multiple Document GET

Example endpoint: http://example.com/xAPI/activities/state

Fetches State ids of all state data for this context (Activity + Agent \[ + registration if specified\]). 
If "since" parameter is specified, this is limited to entries that have been stored or updated since the specified 
timestamp (exclusive). 

**Content:** None.

**Returns:** `200 OK`, Array of State id(s)  

<table>
	<tr><th>Parameter</th><th>Type</th><th>Description</th><th>Required</th></tr>
	<tr id="2.3.s4.table1.row1">
		<td>activityId</td>
		<td>Activity id (IRI)</td>
		<td>The Activity id associated with these states.</td>
		<td>Required</td>
	</tr>
	<tr id="2.3.s4.table1.row2">
		<td>agent</td>
		<td>Agent object (JSON)</td>
		<td>The Agent associated with these states.</td>
		<td>Required</td>
	</tr>
	<tr id="2.3.s4.table1.row3">
		<td>registration</td>
		<td>UUID</td>
		<td>The Registration associated with these states.</td>
		<td>Optional</td>
	</tr>
	<tr id="2.3.s4.table1.row4">
		<td>since</td>
		<td>Timestamp</td>
		<td>Only ids of states stored since the specified Timestamp (exclusive) are returned.</td>
		<td>Optional</td>
	</tr>
</table>

###### <a name="2.3.s5"></a>Multiple Document DELETE

Example endpoint: http://example.com/xAPI/activities/state

Deletes all state data for this context (Activity + Agent \[+ registration if specified\]).  

**Content:** None.

**Returns**: `204 No Content`  
<table>
	<tr><th>Parameter</th><th>Type</th><th>Description</th><th>Required</th></tr>
	<tr id="2.3.s5.table1.row1">
		<td>activityId</td>
		<td>Activity id (IRI)</td>
		<td>The Activity id associated with this state.</td>
		<td>Required</td>
	</tr>
	<tr id="2.3.s5.table1.row2">
		<td>agent</td>
		<td>Agent object (JSON)</td>
		<td>The Agent associated with this state.</td>
		<td>Required</td>
	</tr>
	<tr id="2.3.s5.table1.row3">
		<td>registration</td>
		<td>UUID</td>
		<td>The Registration associated with this state.</td>
		<td>Optional</td>
	</tr>
</table>

<a name="agentsres"></a>

### <a name="2.4">2.4</a> Agents Resource

The Agents Resource provides a method to retrieve a special Object with combined information about an Agent derived from 
an outside service, such as a directory service. This resource has [Concurrency](#concurrency) controls associated with it.

###### <a name="2.4.s1"></a>Combined Information GET

###### <a name="2.4.s2"></a>Details

Example endpoint: http://example.com/xAPI/agents

Return a special, Person Object for a specified Agent. The Person Object is very similar to an Agent Object, 
but instead of each attribute having a single value, each attribute has an array value, and it is legal to 
include multiple identifying properties. This is different from the FOAF concept of person, person is being 
used here to indicate a person-centric view of the LRS Agent data, but Agents just refer to one 
persona (a person in one context).  

The "agent" parameter is a normal Agent Object with a single identifier and no arrays. 
It is not a Person Object, nor is it a Group. 

**Content:** None.

**Returns:** `200 OK`, Person Object

<table>
	<tr><th>Parameter</th><th>Type</th><th>Description</th><th>Required</th></tr>
	<tr id="2.4.s2.table1.row1">
		<td>agent</td>
		<td>Agent object (JSON)</td>
		<td>The Agent representation to use in fetching expanded Agent information.</td>
		<td>Required</td>
	</tr>
</table>

###### <a name="2.4.s3"></a>Requirements
* <a name="2.4.s3.b1"></a>An LRS capable of returning multiple identifying properties for a Person 
Object SHOULD require the connecting credentials have increased, explicitly 
given permissions. 
* <a name="2.4.s3.b2"></a>An LRS SHOULD reject insufficiently privileged requests with `403 Forbidden`.
* <a name="2.4.s3.b3"></a>If an LRS does not have any additional information about an Agent to return, 
the LRS MUST still return a Person Object when queried, but that Person Object will only 
include the information associated with the requested Agent. 

__Note:__ This means that if a request is made for an Agent which the LRS has no 
prior knowledge of, it will still return a Person object containing the information 
about the Agent it received in the request. 

###### <a name="2.4.s4"></a>Person Properties

###### <a name="2.4.s5"></a>Details

<table>
	<tr><th>Property</th><th>Type</th><th>Description</th><th>Required</th></tr>
	<tr id="2.4.s5.table1.row1">
		<td>objectType</td>
		<td>String</td>
		<td><code>Person</code></td>
		<td>Required</td>
	</tr>
	<tr id="2.4.s5.table1.row2">
		<td>name</td>
		<td>Array of strings.</td>
		<td>List of names of Agents retrieved.</td>
		<td>Optional</td>
	</tr>
	<tr id="2.4.s5.table1.row3">
		<td><a href="http://xmlns.com/foaf/spec/#term_mbox">mbox</a></td>
		<td>Array of IRIs in the form "mailto:email address".</td>
		<td>List of e-mail addresses of Agents retrieved.</td>
		<td>Optional</td>
	</tr>
	<tr id="2.4.s5.table1.row4">
		<td><a href="http://xmlns.com/foaf/spec/#term_mbox_sha1sum">mbox_sha1sum</a></td>
		<td>Array of strings.</td>
		<td>List of the SHA1 hashes of mailto IRIs (such as go in an mbox property).</td>
		<td>Optional</td>
	</tr>
	<tr id="2.4.s5.table1.row5">
		<td>openid*</td>
		<td>Array of strings.</td>
		<td>List of openids that uniquely identify the Agents retrieved.</td>
		<td>Optional</td>
	</tr>
	<tr id="2.4.s5.table1.row6">
		<td>account*</td>
		<td>Array of account objects.</td>
		<td>List of accounts to match. Complete account Objects (homePage and name) 
		MUST be provided.</td>
		<td>Optional</td>
	</tr>
</table>

See also: [Agent](./xAPI-Data.md#agent).

###### <a name="2.4.s6"></a>Requirements

* <a name="2.4.s6.b1"></a>All array properties MUST be populated with members with the same definition as the 
similarly named property from Agent Objects.  

* <a name="2.4.s6.b2"></a>Additional properties not listed here SHOULD* NOT be added to this object and each 
property MUST occur only once. 

<a name="activitiesres"></a> 

### <a name="2.5">2.5</a> Activities Resource

The Activities Resource provides a method to retrieve a full description of an Activity from the LRS. 
This resource has [Concurrency](#concurrency) controls associated with it.

###### <a name="2.5.s1"></a>Full Activity Object GET

Example endpoint: http://example.com/xAPI/activities

Loads the complete Activity Object specified.  

**Content:** None.

**Returns:** `200 OK`, Content 
<table>
	<tr><th>Parameter</th><th>Type</th><th>Description</th><th>Required</th></tr>
	<tr id="2.5.s1.table1.row1">
		<td>activityId</td>
		<td>Activity id (IRI)</td>
		<td>The id associated with the Activities to load.</td>
		<td>Required</td>
	</tr>
</table>

###### <a name="2.5.s2"></a>Requirements

* <a name="2.5.s2.b1"></a>If an LRS does not have a canonical definition of the Activity to return, the LRS SHOULD* 
still return an Activity Object when queried.

<a name="agentprofres"></a>

### <a name="2.6">2.6</a> Agent Profile Resource

###### <a name="2.6.s1"></a>Description

The Agent Profile Resource is much like the State Resource, allowing for arbitrary key / document pairs to be saved 
which are related to an Agent. 

###### <a name="2.6.s2"></a>Details

The semantics of the request are driven by the "profileId" parameter. If it is included, the GET method will act upon 
a single defined document identified by "profileId". Otherwise, GET will return the available ids.  

###### <a name="2.6.s3"></a>Single Agent or Profile Document (PUT | POST | GET | DELETE)

Example endpoint: http://example.com/xAPI/agents/profile

Stores, changes, fetches, or deletes the specified Profile document in the context of the specified Agent.  

**Content (PUT | POST):** The document to be stored or updated.  
**Content (GET | DELETE):** None.  

**Returns (PUT | POST | DELETE):** `204 No Content`  
**Returns (GET):** `200 OK`, the Profile document  

<table>
	<tr><th>Parameter</th><th>Type</th><th>Description</th><th>Required</th></tr>
	<tr id="2.6.s3.table1.row1">
		<td>agent</td>
		<td>Agent object (JSON)</td>
		<td>The Agent associated with this Profile document.</td>
		<td>Required</td>
	</tr>
	<tr id="2.6.s3.table1.row2">
		<td>profileId</td>
		<td>String</td>
		<td>The profile id associated with this Profile document.</td>
		<td>Required</td>
	</tr>
</table>

__Note:__ The "agent" parameter is an Agent Object and not a Group. Learning Record Providers wishing to store data
against an Identified Group can use the Identified Group's identifier within an Agent Object. 

###### <a name="2.6.s4"></a>Multiple Document GET

Example endpoint: http://example.com/xAPI/agents/profile

Fetches Profile ids of all Profile documents for an Agent. If "since" parameter is specified, this is limited to entries 
that have been stored or updated since the specified Timestamp (exclusive).  

**Content:** None.

**Returns:** `200 OK`, Array of Profile id(s)  

<table>
	<tr><th>Parameter</th><th>Type</th><th>Description</th><th>Required</th></tr>
	<tr id="2.6.s4.table1.row1">
		<td>agent</td>
		<td>Agent object (JSON)</td>
		<td>The Agent associated with this Profile document.</td>
		<td>Required</td>
	</tr>
	<tr id="2.6.s4.table1.row2">
		<td>since</td>
		<td>Timestamp</td>
		<td>Only ids of Profiles stored since the specified Timestamp 
			(exclusive) are returned.</td>
		<td>Optional</td>
	</tr>
</table>

<a name="actprofres"></a> 

### <a name="2.7">2.7</a> Activity Profile Resource

###### <a name="2.7.s1"></a>Description

The Activity Profile Resource is much like the State Resource, allowing for arbitrary key / document pairs to be saved 
which are related to an Activity. 

###### <a name="2.7.s2"></a>Details

The semantics of the request are driven by the "profileId" parameter. If it is included, 
the GET method will act upon a single defined document identified by "profileId". 
Otherwise, GET will return the available ids.

###### <a name="2.7.s3"></a>Single Document (PUT | POST | GET | DELETE)

Example endpoint: http://example.com/xAPI/activities/profile

Stores, changes, fetches, or deletes the specified Profile document in the context of the specified Activity.  

**Content (PUT | POST):** The document to be stored or updated.  
**Content (GET | DELETE):** None.  

**Returns (PUT | POST | DELETE)** `204 No Content`  
**Returns (GET):** `200 OK`, the Profile document  
<table>
	<tr><th>Parameter</th><th>Type</th><th>Description</th><th>Required</th></tr>
	<tr id="2.7.s3.table1.row1">
		<td>activityId</td>
		<td>Activity id (IRI)</td>
		<td>The Activity id associated with this Profile document.</td>
		<td>Required</td>
	</tr>
	<tr id="2.7.s3.table1.row2">
		<td>profileId</td>
		<td>String</td>
		<td>The profile id associated with this Profile document.</td>
		<td>Required</td>
	</tr>
</table>

###### <a name="2.7.s4"></a>Multiple Document GET

Example endpoint: http://example.com/xAPI/activities/profile

Fetches Profile ids of all Profile documents for an Activity. If "since" parameter is specified, this is limited to 
entries that have been stored or updated since the specified Timestamp (exclusive).  

**Content:** None.

**Returns:** `200 OK`, Array of Profile id(s)  

<table>
	<tr id="2.7.s4.table1.row1"><th>Parameter</th><th>Type</th><th>Description</th><th>Required</th><tr>
	<tr>
		<td>activityId</td>
		<td>Activity id (IRI)</td>
		<td>The Activity id associated with these Profile documents.</td>
		<td>Required</td>
	</tr>
	<tr id="2.7.s4.table1.row2">
		<td>since</td>
		<td>Timestamp</td>
		<td>Only ids of Profile documents stored since the specified Timestamp (exclusive) 
		are returned.</td>
		<td>Optional</td>
	</tr>
</table>


<a name="aboutresource"></a> 

### <a name="2.8">2.8</a> About Resource

###### <a name="2.8.s1"></a>Description

Returns JSON Object containing information about this LRS, including the xAPI version supported.

###### <a name="2.8.s2"></a>Rationale

Primarily this resource exists to allow Clients that support multiple xAPI versions to decide which version to 
use when communicating with the LRS. Extensions are included to allow other uses to emerge.

###### <a name="2.8.s3"></a>Details

###### <a name="2.8.s4"></a>Information GET

Example endpoint: http://example.com/xAPI/about

**Content:** None.

**Returns:** `200 OK`, JSON object containing basic metadata about this LRS
<table border="1">
	<tr><th>Property</th><th>Type</th><th>Description</th><th>Required</th></tr>
	<tr id="2.8.s4.table1.row1">
		<td>version</td>
		<td>Array of version strings</td>
		<td>xAPI versions this LRS supports</td>
		<td>Required</td>
	</tr>
	<tr id="2.8.s4.table1.row2">
		<td>extensions</td>
		<td><a href="./xAPI-Data.md#miscext">Object</a></td>
		<td>A map of other properties as needed</td>
		<td>Optional</td>
	</tr>

</table>

###### <a name="2.8.s5"></a>Requirements

* <a name="2.8.s5.b1"></a>An LRS MUST return the JSON document described above, with a "version" property that includes
the latest minor and patch version the LRS conforms to, for each major version.
    * <a name="2.8.s5.b1.b1"></a>For version 1.0.0 of this specification, this means that `1.0.0` MUST be included;
    `0.9` and `0.95` MAY be included. (For the purposes of this requirement, `0.9` and `0.95`
    are considered major versions.)
* <a name="2.8.s5.b2"></a>Additional properties MUST NOT be added to this object outside of extensions and each 
property MUST occur only once.  
* <a name="2.8.s5.b3"></a>An LRS SHOULD allow unauthenticated access to this resource.
* <a name="2.8.s5.b4"></a>An LRS MUST NOT reject requests based on their version header as would otherwise be 
required by [Versioning](#versioning).

<a name="validation"></a> 

## <a name="3.0">3.0</a> Data Validation

###### <a name="3.0.s1"></a>Description

xAPI内のLRSの機能は、Statementsを保存し、取り出すことである。これらのタスクを実行するのに十分な情報がある限り、それを実行することが期待される。Experience APIにおけるStatementsの検証は、セマンティクスではなくシンタックスにのみ焦点が当てられている。Verb定義、Activityタイプ、および拡張機能の間で有効な意味を保証するルールを実施することは、Statementを送信するLearning Record Providerの責任です。

###### <a name="3.0.s2"></a>Requirements

* <a name="3.0.s2.b1"></a>LRSは構造に関するルールを適用するべきである（SHOULD）。
* <a name="3.0.s2.b2"></a>LRSは意味に関するルールを適用すべきではない。

<a name="concurrency"></a>

### <a name="3.1">3.1</a> Concurrency

##### <a name="3.1.s1"></a>Description
同時実行性制御は、クライアントがLRSに古いデータに基づく文書をPUT、POST、DELETEしないようにする。

##### <a name="3.1.s2"></a>Details
xAPI は、PUT、POST、DELETE が既存のデータを上書きしたり削除したりする可能性のある API の部分において、HTTP 1.1 エンティティタグ  ([ETags](http://www.w3.org/Protocols/rfc2616/rfc2616-sec14.html#sec14.19))) を使用して楽観的な同時実行制御を実装します。

* <a name="3.1.s2.b1"></a>State Resource
* <a name="3.1.s2.b2"></a>Agent Profile Resource 
* <a name="3.1.s2.b3"></a>Activity Profile Resource

##### <a name="3.1.s3"></a>Client Requirements
The State Resource will permit PUT, POST and DELETE requests without concurrency headers, since state conflicts
are unlikely. The requirements below only apply to Agent Profile Resource and Activity Profile Resource.

* <a name="3.1.s3.b1"></a>A Client making a PUT request to either the Agent Profile Resource or Activity Profile 
Resource MUST include the "[If-Match](http://www.w3.org/Protocols/rfc2616/rfc2616-sec14.html#sec14.24)" header or the 
[If-None-Match](http://www.w3.org/Protocols/rfc2616/rfc2616-sec14.html#sec14.26) header.

* <a name="3.1.s3.b2"></a>A Client making a POST request to either the Agent Profile Resource or Activity Profile 
Resource SHOULD* include the "[If-Match](http://www.w3.org/Protocols/rfc2616/rfc2616-sec14.html#sec14.24)" header or the 
[If-None-Match](http://www.w3.org/Protocols/rfc2616/rfc2616-sec14.html#sec14.26) header.

* <a name="3.1.s3.b3"></a>A Client making a DELETE request to either the Agent Profile Resource or Activity Profile 
Resource SHOULD* include the "[If-Match](http://www.w3.org/Protocols/rfc2616/rfc2616-sec14.html#sec14.24)" header.

* <a name="3.1.s3.b4"></a>Clients SHOULD* use the ETag value provided by the LRS rather than calculating it themselves. 

##### <a name="3.1.s4"></a>LRS Requirements

* <a name="3.1.s4.b1"></a>An LRS responding to a GET request MUST add an ETag HTTP header to the response.
* <a name="3.1.s4.b2"></a>An LRS responding to a GET request without using a transfer encoding or using the identity 
transfer encoding MUST calculate the value of the ETag header to be a hexadecimal string of the SHA-1 digest of the contents. 
This hexadecimal string SHOULD be rendered using numbers and lowercase characters only; uppercase characters SHOULD NOT be used. 
The requirement to calculate the ETag this way will be removed in a future version of the specification.
* <a name="3.1.s4.b3"></a>An LRS responding to a GET request using any non-identity transfer encoding MUST NOT calculate 
the included ETag as above, due to the interpretation of ETags by existing web infrastructure.
* <a name="3.1.s4.b4"></a>As defined in [RFC 2616](http://www.w3.org/Protocols/rfc2616/rfc2616-sec14.html#sec14.19), 
an LRS responding to a GET request MUST enclose the header in quotes.  
* <a name="3.1.s4.b5"></a>An LRS responding to a PUT request MUST handle the "[If-Match](http://www.w3.org/Protocols/rfc2616/rfc2616-sec14.html#sec14.24)" header as described in RFC2616, HTTP 1.1 if 
it contains an ETag, in order to detect modifications made after the Client last fetched the document.
* <a name="3.1.s4.b6"></a>An LRS responding to a PUT request MUST handle the "[If-None-Match](http://www.w3.org/Protocols/rfc2616/rfc2616-sec14.html#sec14.26)" header as described in 
RFC2616, HTTP 1.1 if it contains "*", in order to to detect when there is a resource present that the Client is not aware of.
* <a name="3.1.s4.b7"></a>An LRS responding to a POST or DELETE request SHOULD* handle the "[If-Match](http://www.w3.org/Protocols/rfc2616/rfc2616-sec14.html#sec14.24)" header as described in RFC2616, HTTP 1.1 
if it contains an ETag, in order to detect modifications made after the Client last fetched the document.
* <a name="3.1.s4.b8"></a>An LRS responding to a POST request SHOULD* handle the 
"[If-None-Match](http://www.w3.org/Protocols/rfc2616/rfc2616-sec14.html#sec14.26)" header as described in RFC2616, HTTP 1.1 if it 
contains "*", in order to to detect when there is a resource present that the Client is not aware of.

If the header precondition in either of the PUT request cases above fails, the LRS:

* <a name="3.1.s4.b9"></a>MUST return HTTP status `412 Precondition Failed`.
* <a name="3.1.s4.b10"></a>MUST NOT make a modification to the resource. 

If the header precondition in any of the POST or DELETE request cases above fails, the LRS:

* <a name="3.1.s4.b11"></a>SHOULD* return HTTP status `412 Precondition Failed`.
* <a name="3.1.s4.b12"></a>SHOULD* NOT make a modification to the resource. 

If a PUT request is received without either header for a resource that already exists, the LRS:

* <a name="3.1.s4.b13"></a>MUST return HTTP status `409 Conflict`.
* <a name="3.1.s4.b14"></a>MUST return a response explaining that the Learning Record Provider SHOULD
	* <a name="3.1.s4.b14.b1"></a>check the current state of the resource.
	* <a name="3.1.s4.b14.b2"></a>set the "If-Match" header with the current ETag to resolve the conflict.
* <a name="3.1.s4.b15"></a>MUST NOT make a modification to the resource.

<a name="errorcodes"></a> 

### <a name="3.2">3.2</a> Error Codes

##### <a name="3.2.s1"></a>Description

本仕様は，LRS が特定の条件下で，リクエストの受理又は拒否，応答の返却，その他の動作を行うために課される要件を定義する。LRS がリクエストの拒否を要求される場合、適切なエラーコードが要求事項の一部として記載される。

これらの要件はいずれも、LRSが本仕様の範囲外である条件に基づいて、リクエストを拒否し、応答を返す、または異なる動作をするように設定可能であることも許されるという考えと矛盾しない。 

これらの条件の1つは許可である。たとえばLRSは、特定のエージェントに関するステートメントしか発行できないように、特定のクレデンシャルセットにパーミッションを割り当てることができる。そして、そのエージェントに関連しないクレデンシャルを使用したステートメントを拒否することができる。LRSによって割り当てられる許可は、セクション[4.2](#oauthscope)の推奨OAuth Authorizationスコープ値のリストを除けば、この仕様の範囲外である。 

パーミッションは、LRS が GET リクエストに対して返すレスポンスにも影響を与えることができる。たとえば、一連の認証情報は特定のアクターに関するステートメントを閲覧する権限のみを持つかもしれない。この場合、LRSは返されるステートメントをフィルタリングして、そのアクターに関連しないステートメントを除外する。 See [GET Statements](#stmtresget) for details. 

たとえば、LRS は通常ステートメントの "authority" プロパティを上書きするが、ステートメントの提出に使用されたクレデンシャルと強い信頼関係がある場合は、提出された権限を受け入れることができる。See [Authority](./xAPI-Data.md#authority) for details. 

LRSによって設定されたパーミッションによって、技術的に適合したLRSが適合性テストに不合格になることがある。これはテスト用ソフトウェアによる要求が、パーミッションに基づき拒否される場合に起こり得る。このため、LRSは設定可能である必要があり、またはテストに使用される認証情報は、許可制限が適合性テストの結果に影響しないように、十分な許可を付与する必要がある。

もう一つの条件は、送信されたリクエストがLRSによって設定されたサイズ制限を超える場合である。LRSが常にあらゆるサイズのリクエストを受け入れることを期待するのは不合理であろう。LRSは適切と思われるサイズ制限を選択できるが、コンフォーマンステスト中にサイズ制限を適用しないように設定可能である必要がある。もちろん、ハードウェアの制限などにより、コンフォーマンステスト中にもサイズ制限は存在するが、テストの実行に影響を与えない程度に制限することが期待される。

LRSはまた、悪意があると疑われる場合、例えば短時間に予想外の数のリクエストがあった場合、リクエストを拒否したり、クレデンシャルを失効させたりすることができます。この制限は、適合性試験中のリクエストのレートがいかなるレート制限も発動させないように、十分に高くなることが期待される。

##### <a name="3.2.s2"></a>Details
The list below offers some general guidance on HTTP error codes that could be returned from various methods in the API. 

* <a name="3.2.s2.b1"></a>`400 Bad Request` - Indicates
an error condition caused by an invalid or missing argument. The term 
"invalid arguments" includes malformed JSON or invalid Object structures.

* <a name="3.2.s2.b2"></a>`401 Unauthorized` - Indicates that authentication is required, or in the 
case authentication has been posted in the request, that the given credentials have been refused.

* <a name="3.2.s2.b3"></a>`403 Forbidden` - Indicates that the request is unauthorized for the given 
credentials. Note this is different than refusing the credentials given. In this case, the credentials 
have been validated, but the authenticated Client is not allowed to perform the given action.

* <a name="3.2.s2.b4"></a>`404 Not Found` - Indicates the requested resource was not found. May be 
returned by any method that returns a uniquely identified resource, for instance, any State, Agent Profile, 
or Activity Profile Resource request targeting a specific document, or the method to retrieve a single Statement.

* <a name="3.2.s2.b5"></a>`409 Conflict` - Indicates an error condition due to a conflict with the 
current state of a resource, in the case of State Resource, Agent Profile Resource or Activity Profile Resource
requests, or in the Statement Resource PUT or POST calls. See Section [3.1 Concurrency](#concurrency) for more details.

* <a name="3.2.s2.b6"></a>`412 Precondition Failed` - Indicates an error condition due to a failure of 
a precondition posted with the request, in the case of State or Agent Profile or Activity Profile 
API requests. See Section [6.3 Concurrency](#concurrency) for more details.

* <a name="3.2.s2.b7"></a>`413 Request Entity Too Large` - Indicates that the LRS has rejected the Statement or 
document because its size (or the size of an Attachment included in the request) is larger than 
the maximum allowed by the LRS. 

* <a name="3.2.s2.b8"></a>`429 Too Many Requests` - Indicates that the LRS has rejected the request because it 
has received too many requests from the Client or set of credentials in a given amount of time. 

* <a name="3.2.s2.b9"></a>`500 Internal Server Error` - Indicates a general error condition, typically an 
unexpected exception in processing on the server.

##### <a name="3.2.s3"></a>Requirements

* <a name="3.2.s3.b1"></a>An LRS MUST return the error code most appropriate to the error condition from the list above.

* <a name="3.2.s3.b2"></a>An LRS SHOULD return a message in the response explaining the cause of the error.

* <a name="3.2.s3.b3"></a>An LRS SHOULD use content negotiation as described in [RFC 7231](http://tools.ietf.org/html/rfc7231#section-5.3) to decide the format of the error.

* <a name="3.2.s3.b4"></a>An LRS SHOULD allow for plain text, HTML, and JSON responses for errors (using content negotiation).

* <a name="3.2.s3.b5"></a>A Learning Record Provider SHOULD send an "Accept" header with requests to enable content negotiation.

* <a name="3.2.s3.b6"></a>The LRS SHOULD* reject any request with `400 Bad Request` status where the content type header 
does not match the content included in the request or where the structure of the request does not match the structure 
outlined in this specification for a particular content type. For example, if the content of the request is formatted as JSON, 
the content type is expected to be `application/json`. If the content type is application/x-www-form-urlencoded it is expected 
that the request will include a method parameter as outlined in [Alternate Request Syntax](#alt-request-syntax).

* <a name="3.2.s3.b7"></a>The LRS MUST reject with `400 Bad Request` status any requests that use any parameters which the LRS 
does not recognize in their intended context in this specification. 
( __Note:__ LRSs MAY recognize and act on parameters not in this specification).

* <a name="3.2.s3.b8"></a>The LRS MUST reject with `400 Bad Request` status any requests that use any parameters 
matching parameters described in this specification in all but case.

* <a name="3.2.s3.b9"></a>The LRS MUST reject a batch of statements if any Statement within that batch is rejected.

* <a name="3.2.s3.b10"></a>The LRS MUST reject with `403 Forbidden` status any request rejected by the LRS where the 
credentials associated with the request do not have permission to make that request. 

* <a name="3.2.s3.b11"></a>The LRS MUST reject with `413 Request Entity Too Large` status any request rejected by the LRS 
where the size of the Attachment, Statement or document is larger than the maximum allowed by the LRS.

* <a name="3.2.s3.b12"></a>The LRS MAY choose any Attachment, Statement and document size limits and MAY vary this limit 
on any basis, e.g., per authority.

* <a name="3.2.s3.b13"></a>The LRS MUST reject with `429 Too Many Requests` status any request rejected by the LRS where 
the request is rejected due to too many requests being received by a particular Client or set of credentials in a given 
amount of time. 

* <a name="3.2.s3.b14"></a>The LRS MAY choose any rate limit and MAY vary this limit on any basis, e.g., per authority.

The following requirements exist for the purposes of conformance testing, to ensure that any limitations or permissions 
implemented by the LRS do not affect the running of conformance testing software. 

* <a name="3.2.s3.b15"></a>The LRS SHOULD* be configurable not to reject any requests from a particular set of credentials 
on the basis of permissions. This set of credentials SHOULD* be used for conformance testing but MAY be deleted/deactivated 
on live systems. 

* <a name="3.2.s3.b16"></a>The LRS MUST be configurable to accept Attachments, Statements or documents of any reasonable 
size (see above).

* <a name="3.2.s3.b17"></a>The LRS MUST be configurable to accept requests at any reasonable rate. 

<a name="versioning"></a> 

### <a name="3.3">3.3</a> Versioning

###### <a name="3.3.s1"></a>Rationale

将来の仕様改訂により、ステートメントにプロパティが追加されるなどの変更が加えられるかもしれません。セマンティックバージョニングを使用することで、クライアントとLRSは仕様が変更されても、相互運用性を保つことができます。

###### <a name="3.3.s2"></a>Details

バージョン1.0.0から、xAPIは[Semantic Versioning 1.0.0](http://semver.org/spec/v1.0.0.html)に従ってバージョン管理されるようになりました。
クライアントからのリクエストとLRSからのレスポンスには、X-Experience-API-Versionという名前のHTTPヘッダーと、その値としてバージョンが含まれます。たとえば、バージョン 1.0.3 の場合は X-Experience-API-Version : 1.0.3 となります。この仕様の現在のバージョンについては、[改訂履歴](./xAPI-About.md#Appendix1A) を参照してください。


__Note:__ 1.0.0 より後のバージョンの仕様のパッチの場合、「X-Experience-API-Version」ヘッダーは、1.0.x のすべてのバージョンの仕様で常に`1.0.0`である[statement version property](./xAPI-Data.md#version)に一致しません。X-Experience-API-Version」ヘッダにより、LRSとクライアントは、準拠している仕様の正確なパッチバージョンを判断することができます。1.0.xバージョン間で通信の非互換性は発生しないはずですが、以前意図した動作が明確になることがあります。

###### <a name="3.3.s3"></a>LRS Requirements

* <a name="3.3.s3.b1"></a>The LRS MUST include the "X-Experience-API-Version" header in every response.
* <a name="3.3.s3.b2"></a>The LRS MUST set this header to the latest patch version.
* <a name="3.3.s3.b3"></a>The LRS MUST accept requests with a version header of `1.0` as if the version header was `1.0.0`.
* <a name="3.3.s3.b4"></a>The LRS MUST reject requests with version header prior to version 1.0.0 unless such requests are 
routed to a fully conformant implementation of the prior version specified in the header.
* <a name="3.3.s3.b4.1"></a>The LRS MUST reject requests without a version header unless such requests are 
routed to a fully conformant 0.9 implementation.
* <a name="3.3.s3.b5"></a>The LRS MUST accept requests with a version header starting with `1.0.` if the request is otherwise valid. 
* <a name="3.3.s3.b6"></a>The LRS MUST reject requests with a version header of `1.1.0` or greater.
* <a name="3.3.s3.b7"></a>The LRS MUST make these rejects by responding with a `400 Bad Request` error including a short 
description of the problem.

###### <a name="3.3.s4"></a>Client Requirements

* <a name="3.3.s4.b1"></a>The Client MUST include the "X-Experience-API-Version" header in every request.
* <a name="3.3.s4.b2"></a>The Client MUST set this header to the latest patch version.
* <a name="3.3.s4.b3"></a>The Client SHOULD tolerate receiving responses with a version of `1.0.0` or greater.
* <a name="3.3.s4.b4"></a>The Client SHOULD tolerate receiving data structures with additional properties.
* <a name="3.3.s4.b5"></a>The Client SHOULD ignore any properties not defined in version 1.0.0 of the spec.

###### <a name="3.3.s5"></a>Conversion Requirements

* <a name="3.3.s5.b1"></a>Statements of newer versions MUST NOT be converted into a prior version format, e.g., in order 
to handle version differences.
* <a name="3.3.s5.b2"></a>Statements of prior versions MAY be converted into a newer version only by following the methods 
described in [Appendix A: Converting Statements to 1.0.0](#Appendix3A).

<a name="authentication"></a>

## <a name="4.0">4.0</a> Authentication

###### <a name="4.0.s1"></a>Rationale

相互運用性と環境ごとに異なるセキュリティ要件のバランスをとるために、いくつかの認証オプションが定義されています。

###### <a name="4.0.s2"></a>Details
この仕様では、以下の認証方法が定義されている。LRSはこれらのうち少なくとも1つを実装し、さらに本仕様で定義されていない方法を実装するかもしれません。

* <a name="4.0.s2.b1"></a>[OAuth 1.0 (RFC 5849)](http://tools.ietf.org/html/rfc5849)、署名方式は "HMAC-SHA1", "RSA-SHA1", "PLAINTEXT" です。
* <a name="4.0.s2.b2"></a>[HTTP Basic Authentication](http://tools.ietf.org/html/rfc7235)
* <a name="4.0.s2.b3"></a>Common Access Cards

共通アクセスカードは、この仕様の中で認証方法として定義されていますが、この認証方法の実装の詳細は定義されていません。xAPI Working Group は、Common Access Cards を認証方式として実装する LRS 開発者が、この認証方式の詳細を本仕様の将来のバージョンで共同して定義することを推奨しています。

HTTP 基本認証については、[RFC 7235](http://tools.ietf.org/html/rfc7235) で明確に定義されているため、本仕様では詳細を記述しない。

###### <a name="4.0.s3"></a>Requirements

* <a name="4.0.s3.b1"></a>LRS は本仕様で定義される認証方法のうち、少なくとも 1 つを使用した認証をサポートしなければならない。

* <a name="4.0.s3.b2"></a>LRS は、ステートメントの有効性に関する判断、及び使用されたクレデンシャルに基づき実行される可能性のある操作の判断を行う、または委任しなければならない(MUST)。

<a name="authdefs"></a>

### <a name="4.1">4.1</a> OAuth 1.0 Authentication Scenarios and Methods

以下のマトリックスと要件は、OAuth で使用される可能性のある認証シナリオと、これらのシナリオで使用される認証ワークフローを推奨しています。各シナリオで説明されているプロセスは包括的なものではなく、標準的な OAuth ワークフローのバリエーションを概説するものです。

このセクションの要件は、LRS が OAuth 1.0 をサポートしている場合にのみ適用されます。

**registered application** とは、LRSに登録されたOAuthコンシューマとしてLRSに認証を行うアプリケーションのことです。

**known user**とは、LRS上のユーザアカウント、またはLRSがユーザを定義するために信頼するシステム上のユーザを指します。


<table border="1">
<tr><th></th><th>Known user</th><th>User unknown</th></tr>
<tr id="4.1.table1.row1">
<td>Application is registered</td>
<td>Standard workflow for OAuth.</td>
<td>LRS trusts application to access xAPI without additional user credentials. OAuth token steps are not invoked</td>
</tr>
<tr id="4.1.table1.row2">
<td>Application is not registered</td>
<td>The application Agent is not identified as a registered Agent and the LRS cannot make assumptions on its identity.</td>
<td></br></td>
</tr>
<tr id="4.1.table1.row3">
<td>No application</td>
<td>HTTP Basic Authentication is used instead of OAuth, since no application is involved.</td>
<td></br></td>
</tr>
<tr id="4.1.table1.row4">
<td>No authentication</td>
<td align="center"colspan="2">MAY be supported by the LRS, possibly for testing purposes.</td>

</tr>

</table>

##### <a name="4.1.s2"></a>Requirements

* <a name="4.1.s2.b1"></a>The LRS MUST record the application's name and a unique consumer key (identifier).
* <a name="4.1.s2.b2"></a>The LRS MUST provide a mechanism to complete this registration, or delegate to another system 
that provides such a mechanism.
* <a name="4.1.s2.b3"></a>The LRS MUST be able to be configured for complete support of the xAPI:
	* <a name="4.1.s2.b3.b1"></a>With any of the methods below.
	* <a name="4.1.s2.b3.b2"></a>In any of the workflow scenarios below.
* <a name="4.1.s2.b4"></a>The LRS MAY (for security reasons): 
	* <a name="4.1.s2.b4.b1"></a>Support a subset of the methods below.
	* <a name="4.1.s2.b4.b2"></a>Limit the known users or registered applications.
* <a name="4.1.s2.b5"></a>The LRS SHOULD at a minimum supply OAuth with "HMAC-SHA1" and "RSA-SHA1" signatures.

###### <a name="4.1.s3"></a>Application registered + known user Process and Requirements
**Process:** The standard workflow for OAUth 1.0 is used. 

**Requirements:**
* <a name="4.1.s3.b1"></a>The LRS MUST support the resources in [OAuth Authorization Scope](#oauthscope) to complete 
the standard OAuth workflow (details not in this specification).
* <a name="4.1.s3.b2"></a>If this form of authentication is used to record Statements and no authority is specified, the LRS 
SHOULD record the authority as a Group consisting of an Agent representing the registered application, and an Agent 
representing the known user.

###### <a name="4.1.s4"></a>Application registered + user unknown Process and Requirements

**Process:** 
The LRS honors requests that are signed using OAuth with the registered application's credentials and with an empty token 
and token secret.

**Requirements:**
* <a name="4.1.s4.b1"></a>If this form of authentication is used to record Statements, the LRS SHOULD record the authority 
as the Agent representing the registered application.

###### <a name="4.1.s5"></a>Application Not Registered + Known User Process and Requirements

**Process:**
The Learning Record Provider uses a consumer secret consisting of an empty string to call the Temporary Credential 
Request endpoint specifying the "consumer_name" and other usual parameters.  The "consumer_name" contains a string 
representing the application requesting access. 

The Learning Record Provider then sends the user's browser to the Resource Owner Authorization using the temporary 
credentials obtained from the LRS. The Resource Owner Authorization presents a page displaying the "consumer_name" 
plus a warning that the identity of the application requesting authorization cannot be verified.

Otherwise the process follows the standard OAuth workflow. 

**Requirements:**
* <a name="4.1.s5.b1"></a>If this form of authentication is used to record Statements, the LRS MUST record an authority 
that includes both that application and the authenticating user, as a Group, since OAuth specifies an application.

###### <a name="4.1.s6"></a>No Application + Known User Process and Requirements
**Process:**
Use a username/password combination provided by the LRS for use by the known user.

**Requirements:**
* <a name="4.1.s6.b1"></a>If this form of authentication is used to record Statements, the LRS SHOULD 
record the authority as the Agent representing the known user.

###### <a name="4.1.s7"></a>No Authorization Process and Requirements

* <a name="4.1.s7.b1"></a>Requests MUST include headers for HTTP Basic Authentication based on a username and password 
containing zero or more space characters. 
* <a name="4.1.s7.b2"></a>Requests SHOULD* include headers for HTTP Basic Authentication based on a username and password 
each consisting of an empty string. In this case the HTTP Basic Authentication header will be `Basic ` followed by a base64 
encoded version of the string `:`.  This results in the string `Basic Og==`.

This is in order to distinguish an explicitly unauthenticated request from a request that needs to be given a 
HTTP Basic Authentication challenge.

<a name="oauthscope"></a> 

### <a name="4.2">4.2</a> OAuth 1.0 Authorization Scope

##### <a name="4.2.s1"></a>Description
These are recommendations for scopes designed to enable an LRS and an application communicating using the xAPI to 
negotiate a level of access which accomplishes what the application needs while minimizing the potential for misuse. 
The limitations of each scope are in addition to any security limitations placed on the user account associated 
with the request.

Elements of this section draw on [OAuth 2.0](http://tools.ietf.org/html/rfc6749#section-3.3)
despite this section describing requirements for LRS supporting [OAuth 1.0](http://tools.ietf.org/html/rfc5849). 

The requirements in this section only apply if the LRS supports OAuth 1.0.

##### <a name="4.2.s2"></a>Details

The following table lists xAPI scope values:  
<table>
	<tr><th>Scope</th><th>Permission</th></tr>
	<tr id="4.2.s2.table1.row1"><td>statements/write</td><td>write any Statement</td></tr>
	<tr id="4.2.s2.table1.row2">
		<td>statements/read/mine</td>
		<td>read Statements written by "me", that is with an authority 
			matching what the LRS would assign if writing a Statement with 
			the current token.
		</td>
	</tr>
	<tr id="4.2.s2.table1.row3"><td>statements/read</td><td>read any Statement</td>
	<tr>
		<td>state</td>
		<td>read/write state data, limited to Activities and Actors 
			associated with the current token to the extent it is 
			possible to determine this relationship.
		</td>
	</tr>
	<tr id="4.2.s2.table1.row4">
		<td>define</td>
		<td>(re)Define Activities and Actors. If storing a Statement 
			when this is not granted, ids will be saved and the LRS 
			MAY save the original Statement for audit purposes, but 
			SHOULD NOT update its canonical representation of any 
			Actors or Activities.
		</td>
	</tr>
	<tr id="4.2.s2.table1.row5">
		<td>profile</td>
		<td>read/write Profile document data, limited to Activities and Actors 
			associated with the current token to the extent it is 
			possible to determine this relationship.
		</td>
	</tr>
	<tr id="4.2.s2.table1.row6"><td>all/read</td><td>unrestricted read access</td></tr>
	<tr id="4.2.s2.table1.row7"><td>all</td><td>unrestricted access</td></tr>
</table>

###### <a name="4.2.s3"></a>OAuth Resources
<table>
	<tr>
		<th>Name</th>
		<th>Endpoint</th>
		<th>Example</th>
	</tr>
	<tr id="4.2.s3.table1.row1">
		<td>Temporary Credential Request</td>
		<td>OAuth/initiate</td>
		<td>http://example.com/xAPI/OAuth/initiate</td>
	</tr>
	<tr id="4.2.s3.table1.row2">
		<td>Resource Owner Authorization</td>
		<td>OAuth/authorize</td>
		<td>http://example.com/xAPI/OAuth/authorize</td>
	</tr>
	<tr id="4.2.s3.table1.row3">
		<td>Token Request</td>
		<td>OAuth/token</td>
		<td>http://example.com/xAPI/OAuth/token </td>
	</tr>
</table>

##### <a name="4.2.s4"></a>Example
The list of scopes determines the set of permissions that is being requested. For example, an instructor might grant 
"statements/read" to an application (Client), but the LRS would still limit that tool to Statements that the instructor could 
read if querying the LRS with their credentials directly (such as Statements relating to their students).

##### <a name="4.2.s5"></a>Requirements

* <a name="4.2.s5.b1"></a>The LRS MUST accept a scope parameter as defined in [OAuth 2.0](http://tools.ietf.org/html/rfc6749#section-3.3).
* <a name="4.2.s5.b2"></a>The LRS MUST assume a requested scope of "statements/write" and "statements/read/mine" if no 
scope is specified.
* <a name="4.2.s5.b3"></a>The LRS MUST support the scope of "all" as a minimum.
* <a name="4.2.s5.b4"></a>The LRS MAY support other scopes.
* <a name="4.2.s5.b5"></a>The Client SHOULD request only the minimal needed scopes, to increase the chances that the 
request will be granted.
* <a name="4.2.s5.b6"></a>The parameters "consumer_name" and "scope" are not part of OAuth 1.0, and therefore if used MUST be passed 
as query string or form parameters, not in the OAuth header.  

<a name="security"></a>

## <a name="5.0">5.0</a> Security 

認証以外のセキュリティ(OAuthの認可範囲の解釈を含む)については、このドキュメントの現在の範囲を超えており、実装の詳細として個々のLRSプロバイダに任されています。実装者は業界のベストプラクティス、例えばホワイトハウスCIO事務所のThe  [The HTTPS-Only Standard](https://https.cio.gov)に従うことが推奨される。

この仕様の実装において、セキュリティ上の懸念が生じる可能性があり、実装者はセキュリティのために適合性要件を破ることを選択する可能性がある。このような場合、実装者はその実装の決定がセキュリティと相互運用性の両方に影響することを考慮することが推奨される。どのような場合でも、LRSは適合性テストに合格するように設定可能である必要があることに変わりはない。

他のセキュリティの懸念はこの仕様の範囲外であるが、xAPIコミュニティはセキュリティのベストプラクティスを決定することに専念している。この努力は[xAPIsec](https://github.com/xapisec/xapisec)で始まっている。参加は強く推奨される。


<a name="append3"></a>
## <a name="5.0.s1"></a>Appendices

<a name="Appendix3A"></a>

### <a name="A">Appendix A</a>: Converting Statements to 1.0.0

###### <a name="A.s1"></a>Rationale
This is a 1.0.0 specification, and as such implementers do not have to consider prior versions of the specification. 
However, prior versions did see notable adoption. This data conversion is specified in order to preserve the data 
tracked using earlier versions, and make it available to new implementers in a consistent manner.

###### <a name="A.s2"></a>Details

###### <a name="A.s3"></a>Conversion of Statements created based on version 0.9

A 1.0.0 Client or other system converting a Statement created in 0.9 MUST follow the steps below:

* <a name="A.s3.b1"></a>If the Statement has been voided or uses Verbs, Activity types, or properties not included in the
 0.9 specification, do not convert it.
* <a name="A.s3.b2"></a>Prefix "verb" with `http://adlnet.gov/expapi/verbs/`.
* <a name="A.s3.b3"></a>Prefix any Activity ids which are not full absolute IRIs with `tag:adlnet.gov,2013:expapi:0.9:activities:`
* <a name="A.s3.b4"></a>Prefix any extension keys which are not full absolute IRIs with `tag:adlnet.gov,2013:expapi:0.9:extensions:`
* <a name="A.s3.b5"></a>Prefix Activity types with `http://adlnet.gov/expapi/activities/`
* <a name="A.s3.b6"></a>for each Agent (Actor):
    * <a name="A.s3.b6.b1"></a>Search for Inverse Functional Identifiers in this order: "mbox, mbox_sha1sum, openid,
    account". Keep the first populated Inverse Functional Identifier found and discard the rest.
    * <a name="A.s3.b6.b2"></a>For the above Inverse Functional Identifier, take the first element in the array and
    use that as the value of that Inverse Functional Identifier property, discarding any
    remaining elements.
    * <a name="A.s3.b6.b3"></a>If the "name" property is present, set it equal to the first element in the "name"
    array, discard the remaining elements.
    * <a name="A.s3.b6.b4"></a>Remove all remaining properties.
* <a name="A.s3.b7"></a>Remove the "voided" property from the Statement, if present. Remember, if the value of the
  voided property is `true`, then the Statement MUST NOT be converted.
* <a name="A.s3.b8"></a>Add `version": "1.0.0`
* <a name="A.s3.b9"></a>If an authority was not previously set, set the authority to an Agent identified by an account 
with a homePage set to the home page corresponding to the system performing the conversion and an accountName of `unknown`.
* <a name="A.s3.b10"></a>If the "statement" property in Context was set, remove it from the Statement.
* <a name="A.s3.b11"></a>Preserve all other properties without modification, including the "stored" property. The "stored" 
property will still be updated if the Statement is sent to an LRS.

###### <a name="A.s4"></a>Conversion of Statements created based on version 0.95

A 1.0.0 Client or other system converting a Statement created in 0.95 MUST follow the steps below:

* <a name="A.s4.b1"></a>If the Statement is voided, do not convert it.
* <a name="A.s4.b2"></a>Remove the "voided" property from the Statement, if present. Remember, if the value of the "voided" 
property is `true`, then the Statement MUST NOT be converted.
* <a name="A.s4.b3"></a>Add `version": "1.0.0`
* <a name="A.s4.b4"></a>If an authority was not previously set, set the authority to an Agent identified by an account 
with a homePage set to the home page corresponding to the system performing the conversion and an accountName of `unknown`.
* <a name="A.s4.b5"></a>If the Statement property in Context was set to anything other than a StatementRef, 
remove it from the Statement.
* <a name="A.s4.b6"></a>Preserve all other properties without modification, including the "stored" property. The "stored" 
property will still be updated if the Statement is sent to an LRS.


###### <a name="A.s5"></a>Example


A 0.9 Statement:
```
{
    "id": "d1eec41f-1e93-4ed6-acbf-5c4bd0c24269",
    "actor": {
        "objectType": "Person",
        "name": [
            "Joe Schmoe",
            "Joseph Schmoseph"
        ],
        "mbox": [
            "mailto:joe@example.com"
        ],
        "openid": [
            "http://openid.com/joe-schmoe"
        ]
    },
    "verb": "completed",
    "inProgress": false,
    "object": {
        "objectType": "Activity",
        "id": "http://www.example.com/activities/001",
        "definition": {
            "name": {
                "en-US": "Example Activity"
            },
            "type": "course"
        }
    },
    "result": {
        "completion": true
    },
    "context": {
        "instructor": {
            "objectType": "Person",
            "lastName": [
                "Dad"
            ],
            "firstName": [
                "Joe's"
            ],
            "mbox": [
                "mailto:joesdad@example.com"
            ]
        },
        "contextActivities": {
            "parent": {
                "objectType": "Activity",
                "id": "non-absolute-activity-id",
                "definition": {
                    "name": {
                        "en-US": "Another Activity"
                    }
                }
            }
        }
    },
    "timestamp": "2012-06-01T19:09:13.245Z",
    "stored": "2012-06-29T15:41:39.165Z"
}
```

Converted to 1.0.0:
```
{
    "version": "1.0.0",
    "id": "d1eec41f-1e93-4ed6-acbf-5c4bd0c24269",
    "actor": {
        "objectType": "Agent",
        "name": "Joe Schmoe",
        "mbox": "mailto:joe@example.com"
    },
    "verb": {
        "id": "http://adlnet.gov/expapi/verbs/completed",
        "display": {
            "en-US": "completed"
        }
    },
    "object": {
        "objectType": "Activity",
        "id": "http://www.example.com/activities/001",
        "definition": {
            "name": {
                "en-US": "Example Activity"
            },
            "type": "http://adlnet.gov/expapi/activities/course"
        }
    },
    "result": {
        "completion": true
    },
    "context": {
        "instructor": {
            "objectType": "Agent",
            "mbox": "mailto:joesdad@example.com"
        },
        "contextActivities": {
            "parent": [
                {
                    "objectType": "Activity",
                    "id": "tag:adlnet.gov,2013:expapi:0.9:activities:non-absolute-activity-id",
                    "definition": {
                        "name": {
                            "en-US": "Another Activity"
                        }
                    }
                }
            ]
        }
    },
    "timestamp": "2012-06-01T19:09:13.245Z",
    "stored": "2012-06-29T15:41:39.165Z",
    "authority": {
        "objectType": "Agent",
        "account": {
            "homePage": "http://www.example.com",
            "name": "unknown"
        }
    }
}
```


<a name="Appendix3B"></a>

### <a name="B">Appendix B</a>: Table of All Resources

### <a name="B.s1"></a>Required Resources
<table>
	<tr>
		<th>Base Resource Endpoint of the LRS Precedes Each Endpoint</th>
		<th>Function</th>
	</tr>
	<tr id="B.s1.table1.row1">
		<td>statements</td>
		<td>Statement Storage/Retrieval</td>
	</tr>
	<tr id="B.s1.table1.row2">
		<td>agents</td>
		<td>Agent Object Storage/Retrieval</td>
	</tr>
	<tr id="B.s1.table1.row3">
		<td>agents/profile</td>
		<td>Agent Profile Resource</td>
	</tr>
	<tr id="B.s1.table1.row4">
		<td>activities</td>
		<td>Activity Object Storage/Retrieval</td>
	</tr>
	<tr id="B.s1.table1.row5">
		<td>activities/profile</td>
		<td>Activity Profile Resource</td>
	</tr>
	<tr id="B.s1.table1.row6">
		<td>activities/state</td>
		<td>State Resource</td>
	</tr>
	<tr id="B.s1.table1.row7">
		<td>about</td>
		<td>LRS Information</td>
	</tr>
</table>

### <a name="B.s2"></a>OAuth Resources
<table>
	<tr>
		<th>Base Resource Endpoint of the LRS Precedes Each Endpoint</th>
		<th>Function</th>
	</tr>
	<tr id="B.s2.table1.row1">
		<td>OAuth/initiate</td>
		<td>Temporary Credential Request</td>
	</tr>
	<tr id="B.s2.table1.row2">
		<td>OAuth/authorize</td>
		<td>Resource Owner Authorization</td>
	</tr>
	<tr id="B.s2.table1.row3">
		<td>OAuth/token</td>
		<td>Token Request</td>
	</tr>
</table>

<a name="Appendix3C"></a>

### <a name="C">Appendix C</a>: Cross Domain Request Example

[Alternate Request Syntax](#alt-request-syntax) outlines alternative syntax for use when the normal syntax cannot be used due 
to browser or querystring length restrictions. This appendix provides an example of a PUT request to the Statements Resource 
following this format. 

Request using normal syntax:

```
URL: http://example.com/xAPI/statements
Method: PUT

Query String Parameters:
    statementId=c70c2b85-c294-464f-baca-cebd4fb9b348

Request Headers:
    Accept:*/*
    Accept-Encoding:gzip, deflate, sdch
    Accept-Language:en-US,en;q=0.8
    Authorization: Basic VGVzdFVzZXI6cGFzc3dvcmQ=
    Content-Type: application/json
    X-Experience-API-Version: 1.0.3
    Content-Length: 351

Content:
{"id":"c70c2b85-c294-464f-baca-cebd4fb9b348","timestamp":"2014-12-29T12:09:37.468Z","actor":{"objectType":"Agent","mbox":"mailto:example@example.com","name":"Test User"},"verb":{"id":"http://adlnet.gov/expapi/verbs/experienced","display":{"en-US":"experienced"}},"object":{"id":"http://example.com/xAPI/activities/myactivity","objectType":"Activity"}}

```

Request using alternative syntax:

```
URL: http://example.com/xAPI/statements?method=PUT&statementId=c70c2b85-c294-464f-baca-cebd4fb9b348
Method: POST

Request Headers:
    Accept:*/*
    Accept-Encoding:gzip, deflate, sdch
    Accept-Language:en-US,en;q=0.8
    Content-Type: application/x-www-form-urlencoded
    Content-Length: 745

Content (with added line breaks and not URL encoded for readability):
    statementId=c70c2b85-c294-464f-baca-cebd4fb9b348
    &Authorization=Basic VGVzdFVzZXI6cGFzc3dvcmQ=
    &X-Experience-API-Version=1.0.3
    &Content-Type=application/json
    &Content-Length=351
    &content={"id":"c70c2b85-c294-464f-baca-cebd4fb9b348","timestamp":"2014-12-29T12:09:37.468Z","actor":{"objectType":"Agent","mbox":"mailto:example@example.com","name":"Test User"},"verb":{"id":"http://adlnet.gov/expapi/verbs/experienced","display":{"en-US":"experienced"}},"object":{"id":"http://example.com/xAPI/activities/myactivity","objectType":"Activity"}}
```
