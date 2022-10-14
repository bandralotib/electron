# This doc has moved!

* For information on supported releases, see the [Electron Releases](./electron-timelines.md) doc.
* For community support on Electron, see the [Community page](https://www.electronjs.org/community).
* For platform support info, see the [README](https://github.com/electron/electron/blob/main/README.md).
Node.js v18.11.0
► جدول المحتويات
► فِهرِس
► إصدارات أخرى
► خيارات
جدول المحتويات
سطر الأوامر API
ملخص
نقطة دخول البرنامج
تحذير نقطة دخول محمل وحدات ECMAScript
خيارات
-
--
--abort-on-uncaught-exception
--build-snapshot
--completion-bash
-C=conditionو--conditions=condition
--cpu-prof
--cpu-prof-dir
--cpu-prof-interval
--cpu-prof-name
--diagnostic-dir=directory
--disable-proto=mode
--disallow-code-generation-from-strings
--dns-result-order=order
--enable-fips
--enable-source-maps
--experimental-global-customevent
--experimental-global-webcrypto
--experimental-import-meta-resolve
--experimental-loader=module
--experimental-network-imports
--experimental-policy
--no-experimental-fetch
--no-experimental-repl-await
--experimental-specifier-resolution=mode
--experimental-vm-modules
--experimental-wasi-unstable-preview1
--experimental-wasm-modules
--force-context-aware
--force-fips
--frozen-intrinsics
--force-node-api-uncaught-exceptions-policy
--heapsnapshot-near-heap-limit=max_count
--heapsnapshot-signal=signal
--heap-prof
--heap-prof-dir
--heap-prof-interval
--heap-prof-name
--icu-data-dir=file
--input-type=type
--inspect-brk[=[host:]port]
--inspect-port=[host:]port
--inspect[=[host:]port]
تحذير: مفتش ملزم لعنوان IP عام: تركيبة المنفذ غير آمنة
--inspect-publish-uid=stderr,http
--insecure-http-parser
--jitless
--max-http-header-size=size
--napi-modules
--no-addons
--no-deprecation
--no-extra-info-on-fatal-exception
--no-force-async-hooks-checks
--no-global-search-paths
--no-warnings
--node-memory-debug
--openssl-config=file
--openssl-shared-config
--openssl-legacy-provider
--pending-deprecation
--policy-integrity=sri
--preserve-symlinks
--preserve-symlinks-main
--prof
--prof-process
--redirect-warnings=file
--report-compact
--report-dir=directoryوreport-directory=directory
--report-filename=filename
--report-on-fatalerror
--report-on-signal
--report-signal=signal
--report-uncaught-exception
--secure-heap=n
--secure-heap-min=n
--snapshot-blob=path
--test
--test-name-pattern
--test-only
--throw-deprecation
--title=title
--tls-cipher-list=list
--tls-keylog=file
--tls-max-v1.2
--tls-max-v1.3
--tls-min-v1.0
--tls-min-v1.1
--tls-min-v1.2
--tls-min-v1.3
--trace-atomics-wait
--trace-deprecation
--trace-event-categories
--trace-event-file-pattern
--trace-events-enabled
--trace-exit
--trace-sigint
--trace-sync-io
--trace-tls
--trace-uncaught
--trace-warnings
--track-heap-objects
--unhandled-rejections=mode
--update-assert-snapshot
--use-bundled-caو--use-openssl-ca
--use-largepages=mode
--v8-options
--v8-pool-size=num
--watch
--watch-path
--zero-fill-buffers
-cو--check
-eو--eval "script"
-hو--help
-iو--interactive
-pو--print "script"
-rو--require module
-vو--version
متغيرات البيئة
FORCE_COLOR=[1, 2, 3]
NODE_DEBUG=module[,…]
NODE_DEBUG_NATIVE=module[,…]
NODE_DISABLE_COLORS=1
NODE_EXTRA_CA_CERTS=file
NODE_ICU_DATA=file
NODE_NO_WARNINGS=1
NODE_OPTIONS=options...
NODE_PATH=path[:…]
NODE_PENDING_DEPRECATION=1
NODE_PENDING_PIPE_INSTANCES=instances
NODE_PRESERVE_SYMLINKS=1
NODE_REDIRECT_WARNINGS=file
NODE_REPL_HISTORY=file
NODE_REPL_EXTERNAL_MODULE=file
NODE_SKIP_PLATFORM_CHECK=value
NODE_TLS_REJECT_UNAUTHORIZED=value
NODE_V8_COVERAGE=dir
إخراج التغطية
ذاكرة التخزين المؤقت لخريطة المصدر
NO_COLOR=<any>
OPENSSL_CONF=file
SSL_CERT_DIR=dir
SSL_CERT_FILE=file
TZ
UV_THREADPOOL_SIZE=size
خيارات مفيدة V8
--max-old-space-size=SIZE(بالميغا بايت)
--max-semi-space-size=SIZE(بالميغا بايت)
سطر الأوامر API#
يأتي Node.js مع مجموعة متنوعة من خيارات CLI. تعرض هذه الخيارات تصحيح الأخطاء المضمّن وطرق متعددة لتنفيذ البرامج النصية وخيارات وقت تشغيل مفيدة أخرى.

لعرض هذه الوثائق كصفحة دليل في المحطة ، قم بتشغيل man node.

ملخص#
node [options] [V8 options] [<program-entry-point> | -e "script" | -] [--] [arguments]

node inspect [<program-entry-point> | -e "script" | <host>:<port>] …

node --v8-options

نفذ بدون وسيطات لبدء REPL .

لمزيد من المعلومات حول node inspect، راجع وثائق مصحح الأخطاء .

نقطة دخول البرنامج#
نقطة دخول البرنامج عبارة عن سلسلة تشبه المحدد. إذا لم تكن السلسلة مسارًا مطلقًا ، فسيتم حلها كمسار نسبي من دليل العمل الحالي. ثم يتم حل هذا المسار بواسطة محمل وحدة CommonJS . إذا لم يتم العثور على ملف مطابق ، فسيتم طرح خطأ.

إذا تم العثور على ملف ، فسيتم تمرير مساره إلى محمل وحدة ECMAScript في ظل أي من الشروط التالية:

بدأ البرنامج بعلامة سطر أوامر تفرض تحميل نقطة الدخول مع محمل وحدة ECMAScript.
الملف له .mjsامتداد.
لا يحتوي الملف على .cjsامتداد ، ويحتوي أقرب package.jsonملف أصل على حقل مستوى أعلى "type"بقيمة "module".
خلاف ذلك ، يتم تحميل الملف باستخدام محمل وحدة CommonJS. انظر وحدات التحميل لمزيد من التفاصيل.

تحذير نقطة دخول محمل وحدات ECMAScript#
عند تحميل محمل وحدة ECMAScript ، يتم تحميل نقطة دخول البرنامج ، node لن يقبل الأمر إلا كمدخلات فقط مع الملفات ذات الامتدادات .js، .mjsأو .cjs الامتدادات ؛ ومع .wasmملحقات عندما --experimental-wasm-modulesيتم تمكين.

خيارات#
تاريخ
جميع الخيارات ، بما في ذلك خيارات V8 ، تسمح بفصل الكلمات عن طريق الشرط ( -) أو الشرطات السفلية ( _). على سبيل المثال ، --pending-deprecationيعادل --pending_deprecation.

If an option that takes a single value (such as --max-http-header-size) is passed more than once, then the last passed value is used. Options from the command line take precedence over options passed through the NODE_OPTIONS environment variable.

-#
Added in: v8.0.0
Alias for stdin. Analogous to the use of - in other command-line utilities, meaning that the script is read from stdin, and the rest of the options are passed to that script.

--#
Added in: v6.11.0
Indicate the end of node options. Pass the rest of the arguments to the script. If no script filename or eval/print script is supplied prior to this, then the next argument is used as a script filename.

--abort-on-uncaught-exception#
Added in: v0.10.8
Aborting instead of exiting causes a core file to be generated for post-mortem analysis using a debugger (such as lldb, gdb, and mdb).

If this flag is passed, the behavior can still be set to not abort through process.setUncaughtExceptionCaptureCallback() (and through usage of the node:domain module that uses it).

--build-snapshot#
Added in: v18.8.0
Stability: 1 - Experimental
Generates a snapshot blob when the process exits and writes it to disk, which can be loaded later with --snapshot-blob.

When building the snapshot, if --snapshot-blob is not specified, the generated blob will be written, by default, to snapshot.blob in the current working directory. Otherwise it will be written to the path specified by --snapshot-blob.

$ echo "globalThis.foo = 'I am from the snapshot'" > snapshot.js

# Run snapshot.js to intialize the application and snapshot the
# state of it into snapshot.blob.
$ node --snapshot-blob snapshot.blob --build-snapshot snapshot.js

$ echo "console.log(globalThis.foo)" > index.js

# Load the generated snapshot and start the application from index.js.
$ node --snapshot-blob snapshot.blob index.js
I am from the snapshot
The v8.startupSnapshot API can be used to specify an entry point at snapshot building time, thus avoiding the need of an additional entry script at deserialization time:

$ echo "require('v8').startupSnapshot.setDeserializeMainFunction(() => console.log('I am from the snapshot'))" > snapshot.js
$ node --snapshot-blob snapshot.blob --build-snapshot snapshot.js
$ node --snapshot-blob snapshot.blob
I am from the snapshot
For more information, check out the v8.startupSnapshot API documentation.

Currently the support for run-time snapshot is experimental in that:

User-land modules are not yet supported in the snapshot, so only one single file can be snapshotted. Users can bundle their applications into a single script with their bundler of choice before building a snapshot, however.
Only a subset of the built-in modules work in the snapshot, though the Node.js core test suite checks that a few fairly complex applications can be snapshotted. Support for more modules are being added. If any crashes or buggy behaviors occur when building a snapshot, please file a report in the Node.js issue tracker and link to it in the tracking issue for user-land snapshots.
--completion-bash#
Added in: v10.12.0
Print source-able bash completion script for Node.js.

$ node --completion-bash > node_bash_completion
$ source node_bash_completion
-C=condition, --conditions=condition#
Added in: v14.9.0, v12.19.0
Stability: 1 - Experimental
Enable experimental support for custom conditional exports resolution conditions.

Any number of custom string condition names are permitted.

سيتم تطبيق شروط Node.js الافتراضية لـ "node"، "default"و "import"، "require"دائمًا كما هو محدد.

على سبيل المثال ، لتشغيل وحدة نمطية بقرارات "التطوير":

$ node -C=development app.js
--cpu-prof#
تمت إضافته في: الإصدار 12.0.0
الاستقرار: 1- تجريبي
يبدأ تشغيل ملف تعريف وحدة المعالجة المركزية V8 عند بدء التشغيل ، ويكتب ملف تعريف وحدة المعالجة المركزية على القرص قبل الخروج.

إذا --cpu-prof-dirلم يتم تحديده ، يتم وضع ملف التعريف الذي تم إنشاؤه في دليل العمل الحالي.

إذا --cpu-prof-nameلم يتم تحديده ، يتم تسمية ملف التعريف الذي تم إنشاؤه CPU.${yyyymmdd}.${hhmmss}.${pid}.${tid}.${seq}.cpuprofile.

$ node --cpu-prof index.js
$ ls *.cpuprofile
CPU.20190409.202950.15293.0.0.cpuprofile
--cpu-prof-dir#
تمت إضافته في: الإصدار 12.0.0
الاستقرار: 1- تجريبي
حدد الدليل حيث --cpu-profسيتم وضع ملفات تعريف وحدة المعالجة المركزية التي تم إنشاؤها بواسطة.

يتم التحكم في القيمة الافتراضية بواسطة --diagnostic-dirخيار سطر الأوامر.

--cpu-prof-interval#
تمت إضافته في: الإصدار 12.2.0
الاستقرار: 1- تجريبي
حدد الفاصل الزمني لأخذ العينات بالميكروثانية لملفات تعريف وحدة المعالجة المركزية التي تم إنشاؤها بواسطة --cpu-prof. الافتراضي هو 1000 ميكروثانية.

--cpu-prof-name#
تمت إضافته في: الإصدار 12.0.0
الاستقرار: 1- تجريبي
حدد اسم ملف ملف تعريف وحدة المعالجة المركزية الذي تم إنشاؤه بواسطة --cpu-prof.

--diagnostic-dir=directory#
عيّن الدليل الذي تتم كتابة كافة ملفات الإخراج التشخيصية إليه. افتراضات إلى دليل العمل الحالي.

يؤثر على دليل الإخراج الافتراضي لـ:

--cpu-prof-dir
--heap-prof-dir
--redirect-warnings
--disable-proto=mode#
تمت الإضافة في: الإصدار 13.12.0 ، الإصدار 12.17.0
قم بتعطيل Object.prototype.__proto__الخاصية. إذا كان modeالأمر deleteكذلك ، فسيتم إزالة الملكية بالكامل. إذا كان modeالأمر throwكذلك ، فإن عمليات الوصول إلى الخاصية تطرح استثناءً مع الكود ERR_PROTO_ACCESS.

--disallow-code-generation-from-strings#
تمت إضافته في: v9.8.0
اجعل ميزات اللغة المضمنة مثل evalوالتي new Functionتنشئ رمزًا من السلاسل تطرح استثناءًا بدلاً من ذلك. هذا لا يؤثر على node:vmالوحدة النمطية Node.js.

--dns-result-order=order#
تاريخ
عيّن القيمة الافتراضية لـ verbatimin dns.lookup()و dnsPromises.lookup(). يمكن أن تكون القيمة:

ipv4first: يحدد الافتراضي verbatim false.
verbatim: يحدد الافتراضي verbatim true.
الافتراضي هو verbatimوله dns.setDefaultResultOrder()أولوية أعلى من --dns-result-order.

--enable-fips#
تمت إضافته في: v6.0.0
تمكين التشفير المتوافق مع FIPS عند بدء التشغيل. (يتطلب إنشاء Node.js مقابل OpenSSL المتوافق مع FIPS.)

--enable-source-maps#
تاريخ
تفعيل دعم Source Map v3 لتتبع المكدس.

عند استخدام ناقل ، مثل TypeScript ، فإن آثار المكدس التي تم إلقاؤها بواسطة تطبيق تشير إلى التعليمات البرمجية المنقولة ، وليس موضع المصدر الأصلي. --enable-source-mapsيُمكّن التخزين المؤقت للخرائط المصدر ويبذل قصارى جهده للإبلاغ عن تتبعات المكدس المتعلقة بالملف المصدر الأصلي.

Error.prepareStackTraceيمنع التجاوز --enable-source-mapsمن تعديل تتبع المكدس.

ملاحظة ، يمكن أن يؤدي تمكين خرائط المصدر إلى إدخال وقت الاستجابة لتطبيقك عند Error.stackالوصول إليه. إذا كنت تقوم بالوصول Error.stackبشكل متكرر إلى تطبيقك ، فضع في اعتبارك الآثار المترتبة على أداء --enable-source-maps.

--experimental-global-customevent#
تمت إضافته في: الإصدار 18.7.0
كشف CustomEvent Web API على النطاق العام.

--experimental-global-webcrypto#
تمت إضافته في: الإصدار 17.6.0
اكشف عن Web Crypto API على النطاق العالمي.

--experimental-import-meta-resolve#
تمت الإضافة في: الإصدار 13.9.0 ، الإصدار 12.16.2
تفعيل الدعم التجريبي import.meta.resolve().

--experimental-loader=module#
تاريخ
حدد محمل وحدة ECMAScriptmodule التجريبية المخصصة . قد يكون أي سلسلة مقبولة كمحدد .moduleimport

--experimental-network-imports#
تمت إضافته في: الإصدار 17.6.0
الاستقرار: 1- تجريبي
تفعيل الدعم التجريبي https:للبروتوكول في importالمحددات.

--experimental-policy#
مضاف في: v11.8.0
استخدم الملف المحدد كسياسة أمان.

--no-experimental-fetch#
تمت إضافته في: v18.0.0
تعطيل الدعم التجريبي لـ Fetch API .

--no-experimental-repl-await#
مضاف في: v16.6.0
استخدم هذه العلامة لتعطيل انتظار المستوى الأعلى في REPL.

--experimental-specifier-resolution=mode#
تمت الإضافة في: الإصدار 13.4.0 ، الإصدار 12.16.0
يضبط خوارزمية الدقة لحل محددات وحدة ES. الخيارات الصالحة هي explicitو node.

الافتراضي هو explicit، والذي يتطلب توفير المسار الكامل للوحدة النمطية. يتيح nodeالوضع دعم امتدادات الملفات الاختيارية والقدرة على استيراد دليل يحتوي على ملف فهرس.

راجع تخصيص دقة محدد ESM على سبيل المثال الاستخدام.

--experimental-vm-modules#
تمت إضافته في: v9.6.0
تفعيل دعم الوحدة النمطية التجريبية ES في node:vmالوحدة النمطية.

--experimental-wasi-unstable-preview1#
تاريخ
تفعيل دعم واجهة نظام WebAssembly التجريبية (WASI).

--experimental-wasm-modules#
تمت الإضافة في: الإصدار 12.3.0
تفعيل دعم وحدة WebAssembly التجريبية.

--force-context-aware#
تمت الإضافة في: الإصدار 12.12.0
تعطيل تحميل الوظائف الإضافية الأصلية غير المدركة للسياق .

--force-fips#
تمت إضافته في: v6.0.0
فرض التشفير المتوافق مع FIPS عند بدء التشغيل. (لا يمكن تعطيله من التعليمات البرمجية للبرنامج النصي.) (نفس متطلبات --enable-fips.)

--frozen-intrinsics#
تمت إضافته في: الإصدار 11.12.0
الاستقرار: 1- تجريبي
تفعيل الجوهرات التجريبية المجمدة مثل Arrayو Object.

يتم دعم سياق الجذر فقط. ليس هناك ما يضمن أن globalThis.Arrayيكون بالفعل المرجع الجوهري الافتراضي. قد يتم كسر رمز تحت هذا العلم.

للسماح بإضافة polyfill ، --requireيتم تشغيله قبل تجميد العناصر الجوهرية.

--force-node-api-uncaught-exceptions-policy#
تمت إضافته في: الإصدار 18.3.0
يفرض uncaughtExceptionالحدث على عمليات الاسترجاعات غير المتزامنة Node-API.

لمنع وظيفة إضافية موجودة من تعطل العملية ، لا يتم تمكين هذه العلامة افتراضيًا. في المستقبل ، سيتم تمكين هذه العلامة بشكل افتراضي لفرض السلوك الصحيح.

--heapsnapshot-near-heap-limit=max_count#
تمت الإضافة في: الإصدار 15.1.0 ، الإصدار 14.18.0
الاستقرار: 1- تجريبي
يكتب لقطة لكومة V8 على القرص عندما يقترب استخدام كومة V8 من حد الكومة. countيجب أن يكون عددًا صحيحًا غير سالب (في هذه الحالة لن يكتب Node.js أكثر من max_countلقطات إلى القرص).

عند إنشاء لقطات ، قد يتم تشغيل مجموعة البيانات المهملة وتقليل استخدام الكومة. لذلك قد تتم كتابة لقطات متعددة على القرص قبل نفاد الذاكرة في مثيل Node.js. يمكن مقارنة لقطات الكومة هذه لتحديد الكائنات التي يتم تخصيصها خلال الوقت الذي يتم فيه التقاط اللقطات المتتالية. ليس مضمونًا أن يقوم Node.js بكتابة max_countلقطات بالضبط إلى القرص ، ولكنه سيبذل قصارى جهده لإنشاء لقطة واحدة على الأقل وحتى أكثر من max_countاللقطات قبل نفاد ذاكرة مثيل Node.js عندما max_countتكون أكبر من 0.

يستغرق إنشاء لقطات V8 وقتًا وذاكرة (تتم إدارة كل من الذاكرة بواسطة كومة V8 والذاكرة الأصلية خارج كومة V8). كلما كانت الكومة أكبر ، زادت الموارد التي تحتاجها. ستقوم Node.js بضبط كومة V8 لاستيعاب حمل ذاكرة كومة V8 الإضافية ، وستبذل قصارى جهدها لتجنب استخدام كل الذاكرة المتاحة للعملية. عندما تستخدم العملية ذاكرة أكبر مما يراه النظام مناسبًا ، فقد يتم إنهاء العملية فجأة بواسطة النظام ، اعتمادًا على تكوين النظام.

$ node --max-old-space-size=100 --heapsnapshot-near-heap-limit=3 index.js
Wrote snapshot to Heap.20200430.100036.49580.0.001.heapsnapshot
Wrote snapshot to Heap.20200430.100037.49580.0.002.heapsnapshot
Wrote snapshot to Heap.20200430.100038.49580.0.003.heapsnapshot

<--- Last few GCs --->

[49580:0x110000000]     4826 ms: Mark-sweep 130.6 (147.8) -> 130.5 (147.8) MB, 27.4 / 0.0 ms  (average mu = 0.126, current mu = 0.034) allocation failure scavenge might not succeed
[49580:0x110000000]     4845 ms: Mark-sweep 130.6 (147.8) -> 130.6 (147.8) MB, 18.8 / 0.0 ms  (average mu = 0.088, current mu = 0.031) allocation failure scavenge might not succeed


<--- JS stacktrace --->

FATAL ERROR: Ineffective mark-compacts near heap limit Allocation failed - JavaScript heap out of memory
....
--heapsnapshot-signal=signal#
تمت إضافته في: الإصدار 12.0.0
لتمكين معالج إشارة يتسبب في قيام عملية Node.js بكتابة ملف تفريغ كومة الذاكرة المؤقتة عند تلقي الإشارة المحددة. signalيجب أن يكون اسم إشارة صالحًا. معطل بشكل افتراضي.

$ node --heapsnapshot-signal=SIGUSR2 index.js &
$ ps aux
USER       PID %CPU %MEM    VSZ   RSS TTY      STAT START   TIME COMMAND
node         1  5.5  6.1 787252 247004 ?       Ssl  16:43   0:02 node --heapsnapshot-signal=SIGUSR2 index.js
$ kill -USR2 1
$ ls
Heap.20190718.133405.15554.0.001.heapsnapshot
--heap-prof#
تمت إضافته في: الإصدار 12.4.0
الاستقرار: 1- تجريبي
يبدأ تشغيل ملف تعريف الكومة V8 عند بدء التشغيل ، ويكتب ملف تعريف الكومة على القرص قبل الإنهاء.

إذا --heap-prof-dirلم يتم تحديده ، يتم وضع ملف التعريف الذي تم إنشاؤه في دليل العمل الحالي.

إذا --heap-prof-nameلم يتم تحديده ، يتم تسمية ملف التعريف الذي تم إنشاؤه Heap.${yyyymmdd}.${hhmmss}.${pid}.${tid}.${seq}.heapprofile.

$ node --heap-prof index.js
$ ls *.heapprofile
Heap.20190409.202950.15293.0.001.heapprofile
--heap-prof-dir#
تمت إضافته في: الإصدار 12.4.0
الاستقرار: 1- تجريبي
--heap-profحدد الدليل حيث سيتم وضع ملفات تعريف الكومة التي تم إنشاؤها بواسطة .

يتم التحكم في القيمة الافتراضية بواسطة --diagnostic-dirخيار سطر الأوامر.

--heap-prof-interval#
تمت إضافته في: الإصدار 12.4.0
الاستقرار: 1- تجريبي
حدد متوسط ​​الفاصل الزمني لأخذ العينات بالبايت لملفات تخصيص الكومة التي تم إنشاؤها بواسطة --heap-prof. الافتراضي هو 512 * 1024 بايت.

--heap-prof-name#
تمت إضافته في: الإصدار 12.4.0
الاستقرار: 1- تجريبي
حدد اسم ملف ملف تعريف الكومة الذي تم إنشاؤه بواسطة --heap-prof.

--icu-data-dir=file#
مضاف في: v0.11.15
حدد مسار تحميل بيانات وحدة العناية المركزة. (تجاوزات NODE_ICU_DATA).

--input-type=type#
تمت إضافته في: الإصدار 12.0.0
يؤدي هذا إلى تكوين Node.js لتفسير إدخال السلسلة على أنه CommonJS أو كوحدة ES. إدخال سلسلة هو الإدخال عبر --evalأو --printأو STDIN.

القيم الصالحة هي "commonjs"و "module". الافتراضي هو "commonjs".

لا يدعم REPL هذا الخيار.

--inspect-brk[=[host:]port]#
تمت إضافته في: v7.6.0
تنشيط المفتش host:portوفصل في بداية البرنامج النصي للمستخدم. الافتراضي host:portهو 127.0.0.1:9229.

--inspect-port=[host:]port#
تمت إضافته في: v7.6.0
اضبط host:portالمراد استخدامه عند تنشيط المفتش. يفيد عند تنشيط المفتش عن طريق إرسال SIGUSR1الإشارة.

المضيف الافتراضي هو 127.0.0.1.

انظر التحذير الأمني ​​أدناه بخصوص host استخدام المعلمة.

--inspect[=[host:]port]#
تمت إضافته في: v6.3.0
تفعيل المفتش على host:port. الافتراضي هو 127.0.0.1:9229.

يتيح تكامل V8 inspector لأدوات مثل Chrome DevTools و IDEs تصحيح أخطاء ملفات Node.js ومثيلاتها. يتم إرفاق الأدوات بمثيلات Node.js عبر منفذ tcp والتواصل باستخدام بروتوكول Chrome DevTools .


تحذير: مفتش ملزم لعنوان IP عام: تركيبة المنفذ غير آمنة#
يعد ربط المفتش بعنوان IP عام (بما في ذلك 0.0.0.0) بمنفذ مفتوح غير آمن ، لأنه يسمح للمضيفين الخارجيين بالاتصال بالمفتش وتنفيذ هجوم تنفيذ التعليمات البرمجية عن بُعد .

في حالة تحديد مضيف ، تأكد مما يلي:

المضيف لا يمكن الوصول إليه من الشبكات العامة.
جدار الحماية لا يسمح بالاتصالات غير المرغوب فيها على المنفذ.
وبشكل أكثر تحديدًا ، --inspect=0.0.0.0يكون غير آمن إذا كان المنفذ ( 9229افتراضيًا) غير محمي بجدار الحماية.

راجع قسم تصحيح الأخطاء المتعلقة بالضمانات الأمنية لمزيد من المعلومات.

--inspect-publish-uid=stderr,http#
Specify ways of the inspector web socket url exposure.

By default inspector websocket url is available in stderr and under /json/list endpoint on http://host:port/json/list.

--insecure-http-parser#
Added in: v13.4.0, v12.15.0, v10.19.0
Use an insecure HTTP parser that accepts invalid HTTP headers. This may allow interoperability with non-conformant HTTP implementations. It may also allow request smuggling and other HTTP attacks that rely on invalid headers being accepted. Avoid using this option.

--jitless#
Added in: v12.0.0
Disable runtime allocation of executable memory. This may be required on some platforms for security reasons. It can also reduce attack surface on other platforms, but the performance impact may be severe.

This flag is inherited from V8 and is subject to change upstream. It may disappear in a non-semver-major release.

--max-http-header-size=size#
History
Specify the maximum size, in bytes, of HTTP headers. Defaults to 16 KiB.

--napi-modules#
Added in: v7.10.0
This option is a no-op. It is kept for compatibility.

--no-addons#
Added in: v16.10.0, v14.19.0
Disable the node-addons exports condition as well as disable loading native addons. When --no-addons is specified, calling process.dlopen or requiring a native C++ addon will fail and throw an exception.

--no-deprecation#
Added in: v0.8.0
Silence deprecation warnings.

--no-extra-info-on-fatal-exception#
Added in: v17.0.0
Hide extra information on fatal exception that causes exit.

--no-force-async-hooks-checks#
Added in: v9.0.0
Disables runtime checks for async_hooks. These will still be enabled dynamically when async_hooks is enabled.

--no-global-search-paths#
Added in: v16.10.0
Do not search modules from global paths like $HOME/.node_modules and $NODE_PATH.

--no-warnings#
Added in: v6.0.0
Silence all process warnings (including deprecations).

--node-memory-debug#
Added in: v15.0.0, v14.18.0
Enable extra debug checks for memory leaks in Node.js internals. This is usually only useful for developers debugging Node.js itself.

--openssl-config=file#
Added in: v6.9.0
Load an OpenSSL configuration file on startup. Among other uses, this can be used to enable FIPS-compliant crypto if Node.js is built against FIPS-enabled OpenSSL.

--openssl-shared-config#
Added in: v18.5.0
Enable OpenSSL default configuration section, openssl_conf to be read from the OpenSSL configuration file. The default configuration file is named openssl.cnf but this can be changed using the environment variable OPENSSL_CONF, or by using the command line option --openssl-config. The location of the default OpenSSL configuration file depends on how OpenSSL is being linked to Node.js. Sharing the OpenSSL configuration may have unwanted implications and it is recommended to use a configuration section specific to Node.js which is nodejs_conf and is default when this option is not used.

--openssl-legacy-provider#
Added in: v17.0.0
Enable OpenSSL 3.0 legacy provider. For more information please see OSSL_PROVIDER-legacy.

--pending-deprecation#
Added in: v8.0.0
Emit pending deprecation warnings.

Pending deprecations are generally identical to a runtime deprecation with the notable exception that they are turned off by default and will not be emitted unless either the --pending-deprecation command-line flag, or the NODE_PENDING_DEPRECATION=1 environment variable, is set. Pending deprecations are used to provide a kind of selective "early warning" mechanism that developers may leverage to detect deprecated API usage.

--policy-integrity=sri#
Added in: v12.7.0
Stability: 1 - Experimental
Instructs Node.js to error prior to running any code if the policy does not have the specified integrity. It expects a Subresource Integrity string as a parameter.

--preserve-symlinks#
Added in: v6.3.0
Instructs the module loader to preserve symbolic links when resolving and caching modules.

By default, when Node.js loads a module from a path that is symbolically linked to a different on-disk location, Node.js will dereference the link and use the actual on-disk "real path" of the module as both an identifier and as a root path to locate other dependency modules. In most cases, this default behavior is acceptable. However, when using symbolically linked peer dependencies, as illustrated in the example below, the default behavior causes an exception to be thrown if moduleA attempts to require moduleB as a peer dependency:

{appDir}
 ├── app
 │   ├── index.js
 │   └── node_modules
 │       ├── moduleA -> {appDir}/moduleA
 │       └── moduleB
 │           ├── index.js
 │           └── package.json
 └── moduleA
     ├── index.js
     └── package.json
The --preserve-symlinks command-line flag instructs Node.js to use the symlink path for modules as opposed to the real path, allowing symbolically linked peer dependencies to be found.

Note, however, that using --preserve-symlinks can have other side effects. Specifically, symbolically linked native modules can fail to load if those are linked from more than one location in the dependency tree (Node.js would see those as two separate modules and would attempt to load the module multiple times, causing an exception to be thrown).

The --preserve-symlinks flag does not apply to the main module, which allows node --preserve-symlinks node_module/.bin/<foo> to work. To apply the same behavior for the main module, also use --preserve-symlinks-main.

--preserve-symlinks-main#
Added in: v10.2.0
Instructs the module loader to preserve symbolic links when resolving and caching the main module (require.main).

توجد هذه العلامة بحيث يمكن اختيار الوحدة النمطية الرئيسية لنفس السلوك الذي --preserve-symlinksيعطي لجميع الواردات الأخرى ؛ ومع ذلك ، فهي علامات منفصلة للتوافق مع الإصدارات الأقدم من Node.js.

--preserve-symlinks-mainلا --preserve-symlinksيعني تستخدم --preserve-symlinks-mainبالإضافة إلى --preserve-symlinksالحالات التي لا يكون فيها من المرغوب اتباع الارتباطات الرمزية قبل حل المسارات النسبية.

انظر --preserve-symlinksلمزيد من المعلومات.

--prof#
تمت إضافته في: v2.0.0
توليد مخرجات ملف التعريف V8.

--prof-process#
تمت إضافته في: v5.2.0
ناتج منشئ ملفات التعريف العملية V8 الذي تم إنشاؤه باستخدام خيار V8 --prof.

--redirect-warnings=file#
تمت إضافته في: v8.0.0
اكتب تحذيرات العملية إلى الملف المحدد بدلاً من الطباعة إلى stderr. سيتم إنشاء الملف إذا لم يكن موجودًا ، وسيتم إلحاقه به إذا كان موجودًا. إذا حدث خطأ أثناء محاولة كتابة التحذير إلى الملف ، فسيتم كتابة التحذير إلى stderr بدلاً من ذلك.

قد يكون fileالاسم مسارًا مطلقًا. إذا لم يكن الأمر كذلك ، فسيتم التحكم في الدليل الافتراضي الذي ستتم الكتابة إليه بواسطة --diagnostic-dirخيار سطر الأوامر.

--report-compact#
تمت الإضافة في: الإصدار 13.12.0 ، الإصدار 12.17.0
اكتب التقارير بتنسيق مضغوط ، JSON من سطر واحد ، ويمكن استهلاكه بسهولة عن طريق أنظمة معالجة السجل أكثر من التنسيق الافتراضي متعدد الأسطر المصمم للاستهلاك البشري.

--report-dir=directoryوreport-directory=directory#
تاريخ
الموقع الذي سيتم إنشاء التقرير فيه.

--report-filename=filename#
تاريخ
اسم الملف الذي سيُكتب التقرير عليه.

إذا تم تعيين اسم الملف على 'stdout'أو 'stderr'، يتم كتابة التقرير إلى stdout أو stderr للعملية على التوالي.

--report-on-fatalerror#
تاريخ
Enables the report to be triggered on fatal errors (internal errors within the Node.js runtime such as out of memory) that lead to termination of the application. Useful to inspect various diagnostic data elements such as heap, stack, event loop state, resource consumption etc. to reason about the fatal error.

--report-on-signal#
History
Enables report to be generated upon receiving the specified (or predefined) signal to the running Node.js process. The signal to trigger the report is specified through --report-signal.

--report-signal=signal#
History
Sets or resets the signal for report generation (not supported on Windows). Default signal is SIGUSR2.

--report-uncaught-exception#
History
Enables report to be generated when the process exits due to an uncaught exception. Useful when inspecting the JavaScript stack in conjunction with native stack and other runtime environment data.

--secure-heap=n#
Added in: v15.6.0
Initializes an OpenSSL secure heap of n bytes. When initialized, the secure heap is used for selected types of allocations within OpenSSL during key generation and other operations. This is useful, for instance, to prevent sensitive information from leaking due to pointer overruns or underruns.

The secure heap is a fixed size and cannot be resized at runtime so, if used, it is important to select a large enough heap to cover all application uses.

The heap size given must be a power of two. Any value less than 2 will disable the secure heap.

The secure heap is disabled by default.

الكومة الآمنة غير متوفرة على Windows.

انظر CRYPTO_secure_malloc_initلمزيد من التفاصيل.

--secure-heap-min=n#
تمت الإضافة في: الإصدار 15.6.0
عند الاستخدام --secure-heap، --secure-heap-minتحدد العلامة الحد الأدنى للتخصيص من الكومة الآمنة. القيمة الدنيا هي 2. القيمة القصوى هي الأصغر من --secure-heapأو 2147483647. يجب أن تكون القيمة المعطاة أس اثنين.

--snapshot-blob=path#
تمت إضافته في: الإصدار 18.8.0
الاستقرار: 1- تجريبي
عند استخدامه مع --build-snapshot، --snapshot-blobيحدد المسار الذي ستتم كتابة كائن اللقطة الذي تم إنشاؤه عليه. إذا لم يتم تحديده ، فسيتم كتابة blob الذي تم إنشاؤه ، افتراضيًا ، snapshot.blob في دليل العمل الحالي.

عند استخدامه بدون --build-snapshot، --snapshot-blobيحدد المسار إلى البيانات الثنائية الكبيرة التي سيتم استخدامها لاستعادة حالة التطبيق.

--test#
تمت إضافته في: الإصدار 18.1.0
يبدأ تشغيل عداء اختبار سطر الأوامر Node.js. لا يمكن دمج هذه العلامة مع --check، --evalأو --interactive، أو المفتش. راجع الوثائق الخاصة بإجراء الاختبارات من سطر الأوامر للحصول على مزيد من التفاصيل.

--test-name-pattern#
تمت إضافته في: الإصدار 18.11.0
تعبير عادي يقوم بتكوين عداء الاختبار لتنفيذ الاختبارات التي يتطابق اسمها مع النمط المقدم فقط. راجع الوثائق الخاصة بترشيح الاختبارات بالاسم لمزيد من التفاصيل.

--test-only#
تمت إضافته في: v18.0.0
يقوم بتهيئة عداء الاختبار لتنفيذ اختبارات المستوى الأعلى فقط التي تم only تعيين الخيار لها.

--throw-deprecation#
تمت إضافته في: v0.11.14
رمي الأخطاء للإهمال.

--title=title#
تمت إضافته في: الإصدار 10.7.0
تعيين process.titleعند بدء التشغيل.

--tls-cipher-list=list#
تمت إضافته في: v4.0.0
حدد قائمة تشفير TLS افتراضية بديلة. يتطلب إنشاء Node.js مع دعم التشفير (افتراضي).

--tls-keylog=file#
تمت الإضافة في: الإصدار 13.2.0 ، الإصدار 12.16.0
سجل مادة مفتاح TLS في ملف. تكون المادة الأساسية SSLKEYLOGFILE بتنسيق NSS ويمكن استخدامها بواسطة البرامج (مثل Wireshark) لفك تشفير حركة مرور TLS.

--tls-max-v1.2#
تمت الإضافة في: الإصدار 12.0.0 ، الإصدار 10.20.0
اضبط tls.DEFAULT_MAX_VERSIONعلى "TLSv1.2". استخدمه لتعطيل دعم TLSv1.3.

--tls-max-v1.3#
تمت إضافته في: الإصدار 12.0.0
اضبط الإعداد الافتراضي tls.DEFAULT_MAX_VERSIONعلى "TLSv1.3". استخدمه لتمكين دعم TLSv1.3.

--tls-min-v1.0#
تمت الإضافة في: الإصدار 12.0.0 ، الإصدار 10.20.0
اضبط الإعداد الافتراضي tls.DEFAULT_MIN_VERSIONعلى "TLSv1". استخدمه للتوافق مع عملاء أو خوادم TLS القديمة.

--tls-min-v1.1#
تمت الإضافة في: الإصدار 12.0.0 ، الإصدار 10.20.0
اضبط الإعداد الافتراضي tls.DEFAULT_MIN_VERSIONعلى "TLSv1.1". استخدمه للتوافق مع عملاء أو خوادم TLS القديمة.

--tls-min-v1.2#
تمت الإضافة في: الإصدار 12.2.0 ، الإصدار 10.20.0
اضبط الإعداد الافتراضي tls.DEFAULT_MIN_VERSIONعلى "TLSv1.2". هذا هو الإعداد الافتراضي لـ 12.x والإصدارات الأحدث ، ولكن الخيار مدعوم للتوافق مع إصدارات Node.js الأقدم.

--tls-min-v1.3#
تمت إضافته في: الإصدار 12.0.0
Set default tls.DEFAULT_MIN_VERSION to 'TLSv1.3'. Use to disable support for TLSv1.2, which is not as secure as TLSv1.3.

--trace-atomics-wait#
Added in: v14.3.0Deprecated since: v18.8.0
Stability: 0 - Deprecated
Print short summaries of calls to Atomics.wait() to stderr. The output could look like this:

(node:15701) [Thread 0] Atomics.wait(&lt;address> + 0, 1, inf) started
(node:15701) [Thread 0] Atomics.wait(&lt;address> + 0, 1, inf) did not wait because the values mismatched
(node:15701) [Thread 0] Atomics.wait(&lt;address> + 0, 0, 10) started
(node:15701) [Thread 0] Atomics.wait(&lt;address> + 0, 0, 10) timed out
(node:15701) [Thread 0] Atomics.wait(&lt;address> + 4, 0, inf) started
(node:15701) [Thread 1] Atomics.wait(&lt;address> + 4, -1, inf) started
(node:15701) [Thread 0] Atomics.wait(&lt;address> + 4, 0, inf) was woken up by another thread
(node:15701) [Thread 1] Atomics.wait(&lt;address> + 4, -1, inf) was woken up by another thread
The fields here correspond to:

The thread id as given by worker_threads.threadId
The base address of the SharedArrayBuffer in question, as well as the byte offset corresponding to the index passed to Atomics.wait()
The expected value that was passed to Atomics.wait()
The timeout passed to Atomics.wait
--trace-deprecation#
Added in: v0.8.0
Print stack traces for deprecations.

--trace-event-categories#
Added in: v7.7.0
A comma separated list of categories that should be traced when trace event tracing is enabled using --trace-events-enabled.

--trace-event-file-pattern#
Added in: v9.8.0
Template string specifying the filepath for the trace event data, it supports ${rotation} and ${pid}.

--trace-events-enabled#
Added in: v7.7.0
Enables the collection of trace event tracing information.

--trace-exit#
Added in: v13.5.0, v12.16.0
Prints a stack trace whenever an environment is exited proactively, i.e. invoking process.exit().

--trace-sigint#
Added in: v13.9.0, v12.17.0
Prints a stack trace on SIGINT.

--trace-sync-io#
Added in: v2.1.0
Prints a stack trace whenever synchronous I/O is detected after the first turn of the event loop.

--trace-tls#
Added in: v12.2.0
Prints TLS packet trace information to stderr. This can be used to debug TLS connection problems.

--trace-uncaught#
Added in: v13.1.0
Print stack traces for uncaught exceptions; usually, the stack trace associated with the creation of an Error is printed, whereas this makes Node.js also print the stack trace associated with throwing the value (which does not need to be an Error instance).

Enabling this option may affect garbage collection behavior negatively.

--trace-warnings#
Added in: v6.0.0
Print stack traces for process warnings (including deprecations).

--track-heap-objects#
Added in: v2.4.0
Track heap object allocations for heap snapshots.

--unhandled-rejections=mode#
History
Using this flag allows to change what should happen when an unhandled rejection occurs. One of the following modes can be chosen:

throw: Emit unhandledRejection. If this hook is not set, raise the unhandled rejection as an uncaught exception. This is the default.
strict: Raise the unhandled rejection as an uncaught exception. If the exception is handled, unhandledRejection is emitted.
warn: Always trigger a warning, no matter if the unhandledRejection hook is set or not but do not print the deprecation warning.
warn-with-error-code: Emit unhandledRejection. If this hook is not set, trigger a warning, and set the process exit code to 1.
none: Silence all warnings.
If a rejection happens during the command line entry point's ES module static loading phase, it will always raise it as an uncaught exception.

--update-assert-snapshot#
Added in: v18.8.0
Updates snapshot files used by assert.snapshot().

--use-bundled-ca, --use-openssl-ca#
Added in: v6.11.0
Use bundled Mozilla CA store as supplied by current Node.js version or use OpenSSL's default CA store. The default store is selectable at build-time.

The bundled CA store, as supplied by Node.js, is a snapshot of Mozilla CA store that is fixed at release time. It is identical on all supported platforms.

Using OpenSSL store allows for external modifications of the store. For most Linux and BSD distributions, this store is maintained by the distribution maintainers and system administrators. OpenSSL CA store location is dependent on configuration of the OpenSSL library but this can be altered at runtime using environment variables.

See SSL_CERT_DIR and SSL_CERT_FILE.

--use-largepages=mode#
Added in: v13.6.0, v12.17.0
Re-map the Node.js static code to large memory pages at startup. If supported on the target system, this will cause the Node.js static code to be moved onto 2 MiB pages instead of 4 KiB pages.

The following values are valid for mode:

off: No mapping will be attempted. This is the default.
on: If supported by the OS, mapping will be attempted. Failure to map will be ignored and a message will be printed to standard error.
silent: If supported by the OS, mapping will be attempted. Failure to map will be ignored and will not be reported.
--v8-options#
Added in: v0.1.3
Print V8 command-line options.

--v8-pool-size=num#
Added in: v5.10.0
Set V8's thread pool size which will be used to allocate background jobs.

If set to 0 then V8 will choose an appropriate size of the thread pool based on the number of online processors.

إذا كانت القيمة المقدمة أكبر من الحد الأقصى لـ V8 ، فسيتم اختيار القيمة الأكبر.

--watch#
تمت إضافته في: الإصدار 18.11.0
الاستقرار: 1- تجريبي
يبدأ Node.js في وضع الساعة. عندما تكون في وضع الساعة ، تؤدي التغييرات في الملفات المراقبة إلى إعادة تشغيل عملية Node.js. بشكل افتراضي ، سيراقب وضع الساعة نقطة الدخول وأي وحدة مطلوبة أو مستوردة. تُستخدم --watch-pathلتحديد المسارات المراد مشاهدتها.

لا يمكن دمج هذه العلامة مع --check، --evalأو --interactive، أو REPL.

$ node --watch index.js
--watch-path#
تمت إضافته في: الإصدار 18.11.0
الاستقرار: 1- تجريبي
يبدأ Node.js في وضع المراقبة ويحدد المسارات التي يجب مشاهدتها. عندما تكون في وضع الساعة ، تؤدي التغييرات في المسارات المراقبة إلى إعادة تشغيل عملية Node.js. سيؤدي هذا إلى إيقاف تشغيل مشاهدة الوحدات النمطية المطلوبة أو المستوردة ، حتى عند استخدامها مع --watch.

لا يمكن دمج هذه العلامة مع --check، --evalأو --interactive، أو REPL.

$ node --watch-path=./src --watch-path=./tests index.js
هذا الخيار مدعوم فقط على نظامي التشغيل macOS و Windows. سيتم ERR_FEATURE_UNAVAILABLE_ON_PLATFORMطرح استثناء عند استخدام الخيار على نظام أساسي لا يدعمه.

--zero-fill-buffers#
تمت إضافته في: v6.0.0
يملأ صفرًا تلقائيًا جميع الحالات المخصصة والمثيلات Bufferحديثًا SlowBuffer .

-cو--check#
تاريخ
بناء الجملة تحقق من البرنامج النصي دون تنفيذ.

-eو--eval "script"#
تاريخ
قم بتقييم الوسيطة التالية كـ JavaScript. يمكن أيضًا استخدام الوحدات النمطية المحددة مسبقًا في REPL في script.

On Windows, using cmd.exe a single quote will not work correctly because it only recognizes double " for quoting. In Powershell or Git bash, both ' and " are usable.

-h, --help#
Added in: v0.1.3
Print node command-line options. The output of this option is less detailed than this document.

-i, --interactive#
Added in: v0.7.7
Opens the REPL even if stdin does not appear to be a terminal.

-p, --print "script"#
History
Identical to -e but prints the result.

-r, --require module#
Added in: v1.6.0
Preload the specified module at startup.

Follows require()'s module resolution rules. module may be either a path to a file, or a node module name.

Only CommonJS modules are supported. Attempting to preload a ES6 Module using --require will fail with an error.

-v, --version#
Added in: v0.1.3
Print node's version.

Environment variables#
FORCE_COLOR=[1, 2, 3]#
The FORCE_COLOR environment variable is used to enable ANSI colorized output. The value may be:

1, true, or the empty string '' indicate 16-color support,
2 to indicate 256-color support, or
3 to indicate 16 million-color support.
When FORCE_COLOR is used and set to a supported value, both the NO_COLOR, and NODE_DISABLE_COLORS environment variables are ignored.

Any other value will result in colorized output being disabled.

NODE_DEBUG=module[,…]#
Added in: v0.1.32
','-separated list of core modules that should print debug information.

NODE_DEBUG_NATIVE=module[,…]#
','-separated list of core C++ modules that should print debug information.

NODE_DISABLE_COLORS=1#
Added in: v0.3.0
When set, colors will not be used in the REPL.

NODE_EXTRA_CA_CERTS=file#
Added in: v7.3.0
When set, the well known "root" CAs (like VeriSign) will be extended with the extra certificates in file. The file should consist of one or more trusted certificates in PEM format. A message will be emitted (once) with process.emitWarning() if the file is missing or malformed, but any errors are otherwise ignored.

Neither the well known nor extra certificates are used when the ca options property is explicitly specified for a TLS or HTTPS client or server.

This environment variable is ignored when node runs as setuid root or has Linux file capabilities set.

The NODE_EXTRA_CA_CERTS environment variable is only read when the Node.js process is first launched. Changing the value at runtime using process.env.NODE_EXTRA_CA_CERTS has no effect on the current process.

NODE_ICU_DATA=file#
Added in: v0.11.15
Data path for ICU (Intl object) data. Will extend linked-in data when compiled with small-icu support.

NODE_NO_WARNINGS=1#
Added in: v6.11.0
When set to 1, process warnings are silenced.

NODE_OPTIONS=options...#
Added in: v8.0.0
A space-separated list of command-line options. options... are interpreted before command-line options, so command-line options will override or compound after anything in options.... Node.js will exit with an error if an option that is not allowed in the environment is used, such as -p or a script file.

If an option value contains a space, it can be escaped using double quotes:

NODE_OPTIONS='--require "./my path/file.js"'
A singleton flag passed as a command-line option will override the same flag passed into NODE_OPTIONS:

# The inspector will be available on port 5555
NODE_OPTIONS='--inspect=localhost:4444' node --inspect=localhost:5555
A flag that can be passed multiple times will be treated as if its NODE_OPTIONS instances were passed first, and then its command-line instances afterwards:

NODE_OPTIONS='--require "./a.js"' node --require "./b.js"
# is equivalent to:
node --require "./a.js" --require "./b.js"
Node.js options that are allowed are:

--conditions, -C
--diagnostic-dir
--disable-proto
--dns-result-order
--enable-fips
--enable-source-maps
--experimental-abortcontroller
--experimental-global-customevent
--experimental-global-webcrypto
--experimental-import-meta-resolve
--experimental-json-modules
--experimental-loader
--experimental-modules
--experimental-network-imports
--experimental-policy
--experimental-specifier-resolution
--experimental-top-level-await
--experimental-vm-modules
--experimental-wasi-unstable-preview1
--experimental-wasm-modules
--force-context-aware
--force-fips
--force-node-api-uncaught-exceptions-policy
--frozen-intrinsics
--heapsnapshot-near-heap-limit
--heapsnapshot-signal
--http-parser
--icu-data-dir
--input-type
--insecure-http-parser
--inspect-brk
--inspect-port, --debug-port
--inspect-publish-uid
--inspect
--max-http-header-size
--napi-modules
--no-addons
--no-deprecation
--no-experimental-fetch
--no-experimental-repl-await
--no-extra-info-on-fatal-exception
--no-force-async-hooks-checks
--no-global-search-paths
--no-warnings
--node-memory-debug
--openssl-config
--openssl-legacy-provider
--openssl-shared-config
--pending-deprecation
--policy-integrity
--preserve-symlinks-main
--preserve-symlinks
--prof-process
--redirect-warnings
--report-compact
--report-dir, --report-directory
--report-filename
--report-on-fatalerror
--report-on-signal
--report-signal
--report-uncaught-exception
--require, -r
--secure-heap-min
--secure-heap
--snapshot-blob
--test-only
--throw-deprecation
--title
--tls-cipher-list
--tls-keylog
--tls-max-v1.2
--tls-max-v1.3
--tls-min-v1.0
--tls-min-v1.1
--tls-min-v1.2
--tls-min-v1.3
--trace-atomics-wait
--trace-deprecation
--trace-event-categories
--trace-event-file-pattern
--trace-events-enabled
--trace-exit
--trace-sigint
--trace-sync-io
--trace-tls
--trace-uncaught
--trace-warnings
--track-heap-objects
--unhandled-rejections
--update-assert-snapshot
--use-bundled-ca
--use-largepages
--use-openssl-ca
--v8-pool-size
--watch-path
--watch
--zero-fill-buffers
V8 options that are allowed are:

--abort-on-uncaught-exception
--disallow-code-generation-from-strings
--huge-max-old-generation-size
--interpreted-frames-native-stack
--jitless
--max-old-space-size
--perf-basic-prof-only-functions
--perf-basic-prof
--perf-prof-unwinding-info
--perf-prof
--stack-trace-limit
--perf-basic-prof-only-functions, --perf-basic-prof, --perf-prof-unwinding-info, and --perf-prof are only available on Linux.

NODE_PATH=path[:…]#
Added in: v0.1.32
':'-separated list of directories prefixed to the module search path.

On Windows, this is a ';'-separated list instead.

NODE_PENDING_DEPRECATION=1#
Added in: v8.0.0
When set to 1, emit pending deprecation warnings.

Pending deprecations are generally identical to a runtime deprecation with the notable exception that they are turned off by default and will not be emitted unless either the --pending-deprecation command-line flag, or the NODE_PENDING_DEPRECATION=1 environment variable, is set. Pending deprecations are used to provide a kind of selective "early warning" mechanism that developers may leverage to detect deprecated API usage.

NODE_PENDING_PIPE_INSTANCES=instances#
Set the number of pending pipe instance handles when the pipe server is waiting for connections. This setting applies to Windows only.

NODE_PRESERVE_SYMLINKS=1#
Added in: v7.1.0
When set to 1, instructs the module loader to preserve symbolic links when resolving and caching modules.

NODE_REDIRECT_WARNINGS=file#
Added in: v8.0.0
When set, process warnings will be emitted to the given file instead of printing to stderr. The file will be created if it does not exist, and will be appended to if it does. If an error occurs while attempting to write the warning to the file, the warning will be written to stderr instead. This is equivalent to using the --redirect-warnings=file command-line flag.

NODE_REPL_HISTORY=file#
Added in: v3.0.0
Path to the file used to store the persistent REPL history. The default path is ~/.node_repl_history, which is overridden by this variable. Setting the value to an empty string ('' or ' ') disables persistent REPL history.

NODE_REPL_EXTERNAL_MODULE=file#
Added in: v13.0.0, v12.16.0
Path to a Node.js module which will be loaded in place of the built-in REPL. Overriding this value to an empty string ('') will use the built-in REPL.

NODE_SKIP_PLATFORM_CHECK=value#
Added in: v14.5.0
If value equals '1', the check for a supported platform is skipped during Node.js startup. Node.js might not execute correctly. Any issues encountered on unsupported platforms will not be fixed.

NODE_TLS_REJECT_UNAUTHORIZED=value#
If value equals '0', certificate validation is disabled for TLS connections. This makes TLS, and HTTPS by extension, insecure. The use of this environment variable is strongly discouraged.

NODE_V8_COVERAGE=dir#
When set, Node.js will begin outputting V8 JavaScript code coverage and Source Map data to the directory provided as an argument (coverage information is written as JSON to files with a coverage prefix).

NODE_V8_COVERAGE will automatically propagate to subprocesses, making it easier to instrument applications that call the child_process.spawn() family of functions. NODE_V8_COVERAGE can be set to an empty string, to prevent propagation.

Coverage output#
Coverage is output as an array of ScriptCoverage objects on the top-level key result:

{
  "result": [
    {
      "scriptId": "67",
      "url": "internal/tty.js",
      "functions": []
    }
  ]
}
Source map cache#
Stability: 1 - Experimental
If found, source map data is appended to the top-level key source-map-cache on the JSON coverage object.

source-map-cache is an object with keys representing the files source maps were extracted from, and values which include the raw source-map URL (in the key url), the parsed Source Map v3 information (in the key data), and the line lengths of the source file (in the key lineLengths).

{
  "result": [
    {
      "scriptId": "68",
      "url": "file:///absolute/path/to/source.js",
      "functions": []
    }
  ],
  "source-map-cache": {
    "file:///absolute/path/to/source.js": {
      "url": "./path-to-map.json",
      "data": {
        "version": 3,
        "sources": [
          "file:///absolute/path/to/original.js"
        ],
        "names": [
          "Foo",
          "console",
          "info"
        ],
        "mappings": "MAAMA,IACJC,YAAaC",
        "sourceRoot": "./"
      },
      "lineLengths": [
        13,
        62,
        38,
        27
      ]
    }
  }
}
NO_COLOR=<any>#
NO_COLOR is an alias for NODE_DISABLE_COLORS. The value of the environment variable is arbitrary.

OPENSSL_CONF=file#
Added in: v6.11.0
Load an OpenSSL configuration file on startup. Among other uses, this can be used to enable FIPS-compliant crypto if Node.js is built with ./configure --openssl-fips.

If the --openssl-config command-line option is used, the environment variable is ignored.

SSL_CERT_DIR=dir#
Added in: v7.7.0
If --use-openssl-ca is enabled, this overrides and sets OpenSSL's directory containing trusted certificates.

Be aware that unless the child environment is explicitly set, this environment variable will be inherited by any child processes, and if they use OpenSSL, it may cause them to trust the same CAs as node.

SSL_CERT_FILE=file#
Added in: v7.7.0
If --use-openssl-ca is enabled, this overrides and sets OpenSSL's file containing trusted certificates.

Be aware that unless the child environment is explicitly set, this environment variable will be inherited by any child processes, and if they use OpenSSL, it may cause them to trust the same CAs as node.

TZ#
History
The TZ environment variable is used to specify the timezone configuration.

While Node.js does not support all of the various ways that TZ is handled in other environments, it does support basic timezone IDs (such as 'Etc/UTC', 'Europe/Paris', or 'America/New_York'). It may support a few other abbreviations or aliases, but these are strongly discouraged and not guaranteed.

$ TZ=Europe/Dublin node -pe "new Date().toString()"
Wed May 12 2021 20:30:48 GMT+0100 (Irish Standard Time)
UV_THREADPOOL_SIZE=size#
Set the number of threads used in libuv's threadpool to size threads.

Asynchronous system APIs are used by Node.js whenever possible, but where they do not exist, libuv's threadpool is used to create asynchronous node APIs based on synchronous system APIs. Node.js APIs that use the threadpool are:

all fs APIs, other than the file watcher APIs and those that are explicitly synchronous
asynchronous crypto APIs such as crypto.pbkdf2(), crypto.scrypt(), crypto.randomBytes(), crypto.randomFill(), crypto.generateKeyPair()
dns.lookup()
all zlib APIs, other than those that are explicitly synchronous
نظرًا لأن libuv's threadpool له حجم ثابت ، فهذا يعني أنه إذا كان أي من واجهات برمجة التطبيقات هذه يستغرق وقتًا طويلاً لأي سبب من الأسباب ، فإن واجهات برمجة التطبيقات (APIs) الأخرى (التي تبدو غير ذات صلة) التي تعمل في libuv's threadpool ستواجه أداءً متدهورًا. من أجل التخفيف من هذه المشكلة ، يتمثل أحد الحلول المحتملة في زيادة حجم libuv's threadpool عن طريق تعيين 'UV_THREADPOOL_SIZE'متغير البيئة إلى قيمة أكبر من 4(قيمتها الافتراضية الحالية). لمزيد من المعلومات ، راجع وثائق libuv threadpool .

خيارات مفيدة V8#
يحتوي V8 على مجموعة خيارات CLI الخاصة به. node سيتم تمرير أي خيار V8 CLI يتم توفيره إلى V8 للتعامل معه. لا تتمتع خيارات محرك V8 بضمان الاستقرار . لا يعتبرهم فريق V8 أنفسهم جزءًا من API الرسمي الخاص بهم ، ويحتفظون بالحق في تغييرهم في أي وقت. وبالمثل ، لا تغطيها ضمانات الاستقرار Node.js. العديد من خيارات V8 تهم مطوري V8 فقط. على الرغم من ذلك ، هناك مجموعة صغيرة من خيارات V8 التي يمكن تطبيقها على نطاق واسع على Node.js ، وهي موثقة هنا:

--max-old-space-size=SIZE(بالميغا بايت)#
يضبط الحد الأقصى لحجم الذاكرة لقسم الذاكرة القديمة لمحرك V8. مع اقتراب استهلاك الذاكرة من الحد الأقصى ، سيقضي V8 المزيد من الوقت في جمع البيانات المهملة في محاولة لتحرير الذاكرة غير المستخدمة.

على جهاز به ذاكرة 2 جيجا بايت ، ضع في اعتبارك تعيين هذا على 1536 (1.5 جيجا بايت) لترك بعض الذاكرة للاستخدامات الأخرى وتجنب التبديل.

$ node --max-old-space-size=1536 index.js
--max-semi-space-size=SIZE(بالميغا بايت)#
يضبط الحد الأقصى لحجم نصف المساحة لمجمع القمامة في V8 في MiB (ميغا بايت). قد تؤدي زيادة الحجم الأقصى لشبه مساحة إلى تحسين الإنتاجية لـ Node.js على حساب زيادة استهلاك الذاكرة.

نظرًا لأن حجم الجيل الجديد من كومة V8 يبلغ ثلاث مرات (انظر YoungGenerationSizeFromSemiSpaceSizeفي V8) حجم شبه الفضاء ، فإن زيادة 1 ميجابايت إلى شبه مساحة تنطبق على كل من المساحات شبه الفردية الثلاثة وتسبب حجم الكومة إلى زيادة بمقدار 3 ميغا بايت. يعتمد تحسين الإنتاجية على حجم العمل لديك (انظر # 42511 ).

القيمة الافتراضية هي 16 ميجابايت لأنظمة 64 بت و 8 ميجابايت لأنظمة 32 بت. للحصول على أفضل تكوين لتطبيقك ، يجب أن تجرب قيمًا مختلفة لحجم أقصى نصف مساحة عند تشغيل معايير لتطبيقك.

على سبيل المثال ، قياس الأداء على أنظمة 64 بت:

for MiB in 16 32 64 128; do
    node --max-semi-space-size=$MiB index.js
done
