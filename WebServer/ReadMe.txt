V1.5
====

1. ������Ҫͬ���Ĳ���,������ HttpFileServer �ĳ�Ա, ��������. 
��Ҫ�� �ؼ��ζ��� �����̺߳���.

2. ��Ҫ����״̬��Ϣ��, ����  HttpFileServer �� OnError() ����, ����һ���ṹ��.
���� N1, N2 �� STR , ֻ��ֵ, �������ַ���.
�ַ����ֽ��溯������.
ʹ�� SendMessage() ��������.


/////////////////
�ֱ���һ�� HTTPRequest �� HTTPResponse ��, ��װ��Ӧ�Ĳ���.
LinstenProc �� ServiceProc ֻ�����׽��ֲ���, ���շ���. ��������.

1. HTTPRequest.PushData() �������տͻ�������.
2. HTTPResponse.PopData() ������Ӧ���ݸ��ͻ���.
3. HTTPServer������дһ������ GetResponse(),����HTTPRequest����һ����ӦHTTPResponse
��ʹ�ͻ��˵Ĳ���,��ʽ����,����ʹ���˷�GET����,ҲӦ����Ӧ,��ʾ�ͻ���.


// 
V1.52Beta Build 152710

1. ��״̬����ʾ��ǰʹ�õĴ���.
2. ��״̬����ʾ��ǰһ���ж��ٸ�����.

3. _wfindfrist Ӧ�ø�Ϊ _wfindfirst64
4. ��������־ÿ��ֻ�Ƴ�ǰ��100��(ԭ���Ƴ�200��)
5. tagClientInf ���������ֶ�,�ֱ��¼���ӿ�ʼ�����ӽ����� GetTickcount ��ͳ��һ������һ��ռ���˶೤ʱ��.
6. HTTPServer ��� OnRecv() �� OnSend() ����,��ԭ��SericeProc�й��ڽ��պͷ��͵Ĵ���ֱ�����������������,�����߼�������.
ServiceProc �̺߳���ֻ�������� HTTPServer.

7. �����������������

V1.52 Build 152711
OnTimer() û����ȷͬ��. ����: �������ʱ�п��ܻ���΢С�����.

V1.52 Beta 152712
CLIENTINF ����ͳ�Ʒ����ֽ���Ӧ���� __int64 ����.

V1.52 Beta 152713
���д���ͳ�ƴ���,��д��һ������.

V1.52 Beta 152714
1. ���Ŀ¼ʱ,����1G���ļ���ʾΪ GB ������ MB.
2. ���� WSARecv �� WSASend ��ʱ,�Ѽ���������.
3. ͳ�ƴ���ʱ,�ڲ�ʹ��ԭ����ͬ��,�����Ч��.(ԭ��ʹ���ٽ�α���)
4. ���Ӹձ�����ʱ,ֻ��ȥһ��������Ϊ0�� WSARecv ����,�Խ�ʡ��Դ.(���������������û�б�Ҫ.)
5. ��һ��IOCP�̼߳��AcceptEx()������,�������Խ�ʡһ�������߳�,���ҿ�����Ч����������.

V1.52 Beta 153715
1. ��������ť����ɫ.

2. ��������ÿ��IP�����ٸ�����.
������һ��map: key = ipaddress string, value = connection count, OnAccept()�м�����map.

3. ��������ÿ�����ӵ�������.

(1) ��OnSend()��,���㵱ǰ���ӵĴ���,�������ָ��ֵ,��ô����һ����ʱ��,������MS����� OnSend()����,����ǰִ�е�OnSend()ֱ�ӷ���.
������Ҫ��һ��TimerQueue
����ȴ���ʱ�䳬�������ӳ�ʱ,��Ҫ�޸������ӳ�ʱ�������Ӷ����50MSʹ�´ε��� OnSend()ǰ������Ϊ�ٶ�������ʱ���Ͷ����ж�Ϊ������
OnSend()����һ�� bDelay �Ĳ����Ա�ʶ�Ƿ�����ʱ����.

(2) ��һ�ַ���
��OnSend()�м��㵱ǰ����,�������ָ��ֵ,�������СӦ�÷��Ͷ��ٸ��ֽ�,�����ڷ�����󻺳������.
ʹ�����𽥽��͵�ָ��ֵ.

4. �������׽���Ҳ����ɶ˿ڴ���,�Ӵ󲢷���������.

5. ���ӽ���ʱ,����ƽ���ٶ�.ע�����Ϊ0�����.

6. ��������:��һ������ͷ����Ϊ��ν���ʱ,�ᵼ�����ӱ��ر�.

7. �����Ƿ������־������.

8. ���������ļ���־.

9. �ڽ�ֹ���Ŀ¼�������,��������Ĭ���ļ���

10. ����3����ʱ������,�ֱ��Ӧ3�ֶ�ʱ��,���������.

V1.52 Build 152716

V1.52 Build 152718
1. doAccept()�е�OnAccept()������С����.
2. ��־��Ϣ�޸�,����ip��ַ�Ͷ˿ڶ�����һ�е���ǰ��.

===========
V2.00 Beta

Bug Fix list:
1. ִ���������ʱ,��������ɹ����ص��Ǵ��͵��ֽ���Ϊ0�ж�Ϊ�ǿͻ��˹ر�����.
2. HTTPServer::mapServerFile()�� "strFilePath.end()--" ��Ϊ "--strFilePath.end()" ����ȥ������"\"�Եõ���ȷ��·��.
3. �������ƴ������ʱ����,���µĶ�ʱ����Դй©.���������ʱ�ͻ��˹ر������ӽ���������.
4. �Ự��ʱʱ,�ڲ�ȷ����һ���߳�����״���������,ֱ�ӹر����п���ʹ�õ��׽��־��,������һ��ͬ������. ���ڸ��ĻỰ��ʱ�ļ�����.

--------------------
2011-12-04
��ҪĿ��: ��� FastCGI ֧��,ʵ�� remote ģʽ,������ locale ģʽ��չ.
���� remote ���� locale ֻ������ͨ��������,����ĺ��Ĵ��벻Ӧ���ܴ�Ӱ��.

��������ģ���ԭ��: ����ʱ��,ÿ���׽���ֻ��һ��������һ��д����һ����һ��д����.

0. ���� - CGI �� FastCGI

0.1 ʲô��CGI? ����һ����׼,���(http://tools.ietf.org/html/rfc3875),վ��Web�������ĽǶ�,������ҵķ�����֧��CGI?
0.1.1 �� UNIX ������, ͨ�� pipe(), fork(), execve(), dup(), dup2() �Ⱥ�����Web Server���̴��� CGI �ӽ���,���Ұ� stdin �� stdout �ض��򵽹ܵ�,
ͬʱ��HTTP��������һ�� env ��,ͨ�� execve() ���ݵ� CGI �ӽ��̴Ӷ�ʵ�� Web Server �� CGI Process ֮������ݴ���.
0.1.2 ��Windows ������, ʹ���ļ�ϵͳ: Web Server �Ѳ���д��һ����ʱ�ļ�Ȼ������ CGI �ӽ���, CGI �ӽ��̰Ѵ��������Ϊָ������һ���ļ�.

0.2 ʲô�� FastCGI? ����һ������Э��,���(http://www.fastcgi.com/).
0.2.1 FastCGI Application �б���ģʽ��Զ��ģʽ��������ģʽ. ��� FastCGI Application ������Զ��,��ôFastCGI Application������
һ��TCP�˿�, Web Server���Ӹö˿ں��� FastCGI Э����֮��������.
0.2.2 ����� Unix ����,����ʹ�� Unix���׽���(�����ڹܵ�)����,�����Windows����ֻ����TCP������.
0.2.3 ���ӽ�����,���� FastCGI Э�齻������,���� FastCGI Application ����������,�������ӿ��Ա���,������ÿ�ζ��ر�.

����,���Բο� Lighttpd ��Դ����.

1. Ҫ֧��POST����,�ͻ��˵ݽ���������һ��HTTPContent����, FastCGI ģ��Ӹö����ȡ����.

1.1 HTTPContent ����ӿͻ��˶�ȡ����,����chunked����? ���ټ�¼ͳ������,Ȼ���ٵݽ��� FastCGI ����.
1.2 

2. FastCGI ����Ҳһ������ɶ˿��߳�����, �� CFastCGIConn ��װ, ������tagClientInf��.

2.1 CFastCGIConn ����
2.1.1 Connect(),Close()��.
2.1.2 Proc(),��Ϊ�����¼���ɺ�Ļص�����,�ڸú����ڲ���� FastCGI Э��涨�Ķ���.

3. �Ƿ�ά��һ�� CFastCGIConn ���ӳ�?

4. �Ƿ�ά��һ�� FastCGI Application �Ľ��̳�?

2011-12-05

1. ���� CFastCGIFactory ����ά������FastCGI���̳غ����ӳ�.
1.1 CFastCGIFactory::GetConnection() ����һ����ԾFCGI����.
1.2 CFastCGIFactory::Catch() ������չ����PHP�ж��Ƿ��� FastCGI����ǰ����,�����������Ĭ�ϴ���.
1.3 CFastCGIFactory���������,�߼������еĺ�������ȫ���� CFastCGIConn ����,���Բ�������Response����,��CFastCGIConnֱ�Ӳ����ͻ��������׽���.

2011-12-06

1. ��������ģ��, IOCPNetwork, ���𴴽��׽���,�ر��׽���,����ʱ�����а��������ӳ�ʱ�ͻỰ��ʱ.
�ϲ�ģ��ͨ�� intptr_t (����SOCKET���) ����,���ǲ�ֱ�Ӳ����׽���.
����һ������ӿ�,�������ܻص��¼�,�� OnRead() OnRecv() OnClose() OnTimeout() ��.
����ֻ��һ���ص�����resultfunc_t,��Ϊ��������GetQueuedCompletionStatus()�ķ��ؽ��,����ģ�鲢��֪����send,recv����accept.

���� IOCPNetwork �������׽���,ֻ��ͨ�� registerSocket(bool add_or_remove) �Ǽ�/ȡ�� Ҫ��IOCP������׽���.
�����ƺ�������һЩ.

2. HTTPServer
2.1 HTTPServer::CatchFastCGIRequest() ����FastCGI����
2.2 HTTPServer::ReleaseFastCGIRequest() FastCGIģ�鴦����FastCGI�����,���øú����Ի�����Դ.

3. ���Ĵ���(���˽���)ȥ��MFC����
3.1 �� _beginthreadex ���� _beginthread ���� AfxBeginthread
3.2 ����������ʱ�⺯��(C/C++��׼�⺯�� > Microsoft CRT (MS �Ա�׼�����չ) > ֱ�ӵ���Windows API) / ���ݽṹ��STL,��Ҫ��MFC�Ŀ�.
3.3 �����ڸ������ڱ�дANSI���ݵ�UTF-8����ĳ��������UNICODE��,��Ϊ�������õ�����,ֻ��windowsƽ̨������Щ w_**** ����.
��������Ϊ ANSI���ݵĳ�����ǳ���ı�����Ŀ,����������˵����ֻ�Ǳ��뷽ʽ����Ӱ������߼�,��ȫ��ʹ��UNICODE�汾��API����С�������ʱ����������ȫû������. UNICODE�����Ǳ�Ҫ�Ķ����Ǻõ�,��UNICODE��������ANSI��������д���벻����û��Ҫ�Ķ������޴���.Ҫ���������������
��LINUXһ��,������UTF-8,�����ӿ���ANSI,��ʾ������UTF-8���ǺϺ��߼���,�����Ľ������.

2011-12-07

1. ����󶨵�������ĳ��IP��ַ��������,������־���߽����ĳ��λ����ʾ��ǰ�󶨵�IP��ַ.

2. ��HTTPServer�а���һ�� ServerEnv ��Ϊ asp.net / jsp / php ���ʱ�õ��� "server"�����ʵ��.
ֻ�ṩһЩ��̬��,��Ҫ���⹫��������.
2.1 mapPath()
2.2 maxConnections()
2.3 maxSpeed() / maxConnSpeed()
2.4 sessionTimeout()
2.5 deadTimeout()
2.6 rootPath();
2.7 isDirectoryVisible();
2.8 port();
2.9 ipAddress();
2.10 defaultFileNames();
2.11 curConnectionsCount(); // �� SOCKINFMAP.size() �ظ���.

3. ���԰� ServerEnv ���ݸ���ͨ����(�� HTTPServer �������) ���� �κ�����֧�ֵ�������FastCGI����.

4. HTTPApplication ��ʾ���HTTPӦ��,����HTTPServer����Ϊ HTTPServer ��������ʾHTTPӦ���е�һ������,���������������Ͻ������վһ��.
HTTPServerӵ���Լ�������ģ��,�����Լ�����������. HTTPApplication ֻ��ά��һ������HTTPServerʵ��.
�ƺ�Ҳûʲô��Ҫ...HTTPApplication�Ĺ���̫����,û�д��ڵı�Ҫ,�������ֱ�Ӵ������ HTTPServerʵ������.

2011-12-08

1. HTTPServer ���һ�� ServerEnv ����,����ά�� "������" ��صľ�̬��Ϣ������,�� PHP �� SERVER ��ʵ��,��Ҫ�� ServerEnv ���󴫵ݸ� 
HttpConnection �� FastCGIConnection.

2. �߼�����Ҫ HttpConnection ������ͨ��HTTP���Ӻ� FastCGIConnection ����FastCGI ����,�������� HttpConnection ���ܲ�����,����ֱ�ӰѴ���
�ϲ��� HTTPServer ��.

3. FastCGIConnection::proc(ServerEnv* svr ...) HTTPServer����proc()�ķ���ֵ�ж� FastCGI ģ���Ƿ��Ѿ���������������Ի�����Դ.

==================
2011-12-21

1. �����ȶ���(��С��)��һ���߳�ʵ�ֶ�ʱ��. ���ǲ�Ҫʹ�� Timer Queue, Timer Queueʹ����̫���߳�.

����һ��WaitableTimer��һ��Event,��¼����ĳ�ʱʱ��. ��ʱ���߳�ʹ�� Muti-Wait�ȴ���2������.
�����µĶ�ʱ����Ҫ����ʱ,SetEvent�Ƕ�ʱ�߳�����,Ȼ��Ƚϵõ���Ҫ�ȴ���ʱ��,�ٵ��� SetWaitbleTimer.


2. ������������صĹ���,���ͽ��ճ�ʱ,�ٶ����Ƶȶ����е�����ģ����.����һ���������߳�����ִ����ʱ����,��ʱ�����ں�ֻ������ʱ����,Ȼ��ͷ��ؾ������ٶ�ʱ���̵߳�ִ��ʱ��.

3. ������ģ������в���������ʵ������Ŀ��
3.1 ����ͬʱ��һ�����������һ����������.
3.2 ����ʱ����.
3.3 ���е������Ʒ����ٶ����ƺͽ����ٶ�����.

���еĲ��������������������,��Ϊ�ص�������������,��Ȼ���綯������˳��ִ��,���ǻص��������Բ���ִ��.

2011-12-22
1. ����ģ��ֻʵ�ֶ�IOCP���߳�ģ�͵���С��װ,�Ȳ���ͬ������Ҳ������ OVERLAPPED ���ݽṹ.
����ṹ IOCPOVERLAPPED ��һ���ֶ��Ա���ص������ĵ�ַ.
�����������,Ҫ�ﵽ�������պͷ���ǰ���µĳ�ʱ����,��Ҫͬ�����ƶ����ϲ������Ҳ��Ҫ��ͬ������,������Ϊ����ģ�黹������С���.

2. �ö��к�WaitableTimerʵ�ֶ�ʱ����. ��Ϊ��ʱ,�ٶ����ƵĶ�ʱ��.
�Ự��ʱ������ OnSend �� OnRecv�м��,���Ч��.

2012-1-2
1. �� QueryPerformanceCounter ʵ���˾���1ms�Ķ�ʱ������. ��Ȼ�Ա�����ûʲô����.

2012-1-18
1. ���ƻ�ȥ��... IOCPNetwork �����ص��ṹ,�ṩ��ʱ,�ٶ����ƹ���,���������������Ӧ�õ�FCGIģ����?
2. ��ʱIHTTPServer�ӿ�,������ģ��(��FCGI)�ص�,����HTTPServer���ܻ����Ϣ,���ѷ��͵��ֽ���,�Ƿ�رյ�.


2012-2-5
1. HTTPServer����ֻ���������׽���,�����ӱ����ܺ�, HTTPServer�������url��չ�������ʹ�����ͬ���͵�HTTP���Ӷ���.
HTTPConnection ���� FCGIConnection.
2. HTTPConnection�������һ����ͨ��HTTP����,Ŀ¼�б���߾�̬�ļ�.ֱ�Ӳ�������ģ��,����ص�����.
3. FCGIConnection�������FCGI����.ֱ�Ӳ�������ģ��,����ص�����.
4. HTTPConnection �����Ӷ�����������֮��,�ص� HTTPServer ����� onClose �ӿ�,����������Դ.

2012-2-9
1. HTTPContent ������ HTTPRequest �� HTTPResponse ��,���ⲿ���ɼ�.
2. HTTPRequest �� HTTPResponse �ֱ��ṩ push �� pop ����,һ��ֻд,һ��ֻ��.
3. HTTPResponse �ṩ setFile �� setData ���������ļ���������,���� HTTPContent �Ĵ���.

2012-2-13
1. HTTPRequest �ṩ recvFromClient ����,���ҹ���socket buffer, HTTPServer�����ڽ��յ��¿ͻ����Ӻ�,ֻ����һ�� HTTPRequest ����,
Ȼ����� recvFromClient(). ����ģ����Ȼ�� HTTPServer ����.
2. HTTPResponse �ṩ sendToClient ����,ͬ��.
3. FCGIResponse �ṩ recvFromFCGI, sendToFCGI, sendToClient ����.
4. ������ HTTPConnection ����Ĵ���.

5. HTTPRequest �� IResponse �ֱ��ṩ����ͳ�Ƶĺ���,������պͷ��͵�����.


========================================
1. һ��connection��Ϊ�����߼�����
1.1 HTTPRequest,������պͽ���HTTP����,�����Ӧ�������¼�.
1.2 HTTPResponder,��������Ӧ,�����Ӧ�������¼�.

2. IHTTPServer �ṩ onRequest �� onResponser �ص�.

3. FCGIResponder �� HTTPResponder �������Խӿ� IResponder

4. HTTPResponseHeader

2012-2-14
1. ֧�� keep-alive ѡ��.���ڱ����������ڴ���������.

================================

2012-2-17
ֻʣ��FCGIResponder��Ҫ������.

1. ��һ�� memfile ��ΪFCGI���ͻ���,���԰Ѷ���䳤��FCGIRecordд��memfile,Ȼ��������memfile ֮��,������һ������
�����ͽ����ʹ�ù̶������������������.

2. ������ FCGI_BEGIN_REQUEST�� FCGI_PARAMS֮��,�ͽ�������ӵ�״̬
2.1 ��HTTP��ȡSTDIN
2.2 ����STDIN��FCGI
2.3 ��FCGI��ȡSTDOUT
2.4 ����STDOUT��HTTP
�����Ĳ�����ͬʱ����,ͬ������Ӧ����ô����?

2012-2-22
1. �������ͳɹ����Ϊ�����ߴ��� FCGIResponder
1.1 HTTP -> STDIN
1.2 STDOUT -> HTTP
�������߿��Բ�������,ֻ��Ҫ��������������.
ģ�� FCGIContent , ��� eof() ֻ���յ� FCGI_END_REQUEST ֮�� eof() �ŷ���true.

2012-2-23
FCGIWriterPipe - ���ƹ������ķ�ʽ,����ͨ��������FCGIPipe �õ�����ú���������.
FCGIReaderPipe - �Ѵ�FCGIServer�յ�����������,�õ���������ͨ������
��Ҫ���Լ��Ļ�����.

2012-2-28
phpinfo()�����Ѿ��ܳɹ����еõ����.
������Ҫ�ٿ��ǳ���ṹ��������.
Ŀ��:�����ٵĻ�����ʵ��.

ʵ��һ�����ƹܵ��� socket_buffer_t, ��FCGI server �յ����ݺ����д�뻺��,�ֶ��Ҳû����,��С�����Զ�����.

2012-3-2
2.0�汾���Ҫ������:
1. ȥ�� UNICODE, ����ʹ�� ANSI-UTF8��̱ȽϺ�. ���ǳ���ı�Դ. �ַ������������ʾ����.
2. �� HTTPConf �ౣ������XML��ʽ.


2012-3-6
FCGIResponder �չ�. 
���ڿ��� FCGIFactory ����ģ�������
1. Զ��FCGI server ���ӵ�ͳһ����,����.
2. ����FCGI ���̵Ĺ���,����.
3. ������ͻָ�,Զ��TCP���Ӷ˿�,���ؽ�������Ӧʱ,Ӧ����ô��.
4. ͬһ��TCP/PIPE,���FCGI���󲢷�ʱ,��ô��.

2012-3-9
���ڶ�� FCGIResponder ��Ҫ����ͬһ��FCGI����(�׽��ֻ��߹ܵ�),���Ա����� FCGIFactory ������FCGI����.
�����Բ�ͬ�� FCGIResponder �ķ��������Ŷ�,��ȷ���������� FCGI Record ��������.
ͬʱҲ��Ҫ�� �������� �Ŷ�: FCGIFactory ���������ƵĻ������� FCGI���ӵ�����(�����ڴ�����),
������ FCGIResponder �ύ��������֮���ʹ�� FCGI������ȡ����,������Ҫ��֤ FCGI record ��������.

2012-3-11
������ FCGIResponder ����ͬһ��FCGI����,��ô���� FCGIResponder ���໥Ӱ��,�ٶȿ�Ŀͻ�����Ҫ�ȴ��ٶ����Ŀͻ���.
��Ϊ���ܻ����������.
��һ��˼·:  FCGIFactory ʵ��һ�����ӳ�,��ÿ�� FCGIResponder ����һ��������FCGI����,��������.����,��Ȼ�������Ķ�һЩ,����
�ṹ�ϱȽϼ�,�����໥֮�䲻��Ӱ��.
ȱ��: �����������ܵ�����,�����Ǳ���ģʽ��, �޷����������FCGI server����,���ĳ���ͻ��˵���Ӧʱ�䳤�ͻᵼ�¸�FCGI����(����)
һֱ��ռ��.
�ڱ�����Զ��ģʽ����FCGIserver��һ�����з���,���� nginx ����.

2012-3-12
����ʹ�����ӳصķ���,��������һ���ȴ����в���¼���ʱ��(����getConnection() ���ṩһ���ص�����). �������ӱ��ͷ�ʱ(�� releaseConnection
������ʱ)�鿴�ȴ�����,����� FCGIResponder ���ڵȴ�����ûص�����,ͬʱҪ���ȴ�ʱ��,����ȴ�ʱ�����,���� HTTP 503.
����ȴ����й���,���Ƴ���ͷ��¼������ HTTP503.

Զ��ģʽ��,�׽��ֵ� connect ������ FCGIFactory ��ִ�л��� FCGIResponder ��ִ����?
�߼��Ͽ���Ӧ���� FCGIFactory, ������ connect ��һ���첽����,����� FCGIFactory ִ��,�����Ҫ�ص�����.

2012-3-13
connect ������ FCGIFactory ִ��, �����׽��ֺ�,����æµ����,����FCGI����״̬Ϊ CONNECTING,ͬʱ FCGIResponder ����ȴ�����.
������ɺ�,�ص�.
ԭ��: ���� getConnection �õ���FCGI���Ӷ��ǿ�ֱ���õ�����.

2012-3-14
��FCGI Windows NT�������ܵ���ʹ���������.
����һ�� PHP-CGI ����ͬʱֻ�ܴ���һ������(��Ϊֻ��һ�������ܵ�ʵ����STDIN),���������ܵ�, HTTP server ������֪����������һ�������ܵ�ʵ��(PHP-CGI)�ڴ���ǰ����,����ʹ�ò�ͬ�Ĺܵ�����.
����Ҫʵ��һ�����̳�,������ά�� PHP-CGI ����. FCGIProcessContainer
�ж��ٸ� PHP-CGI ���̾��ж��ٸ������ܵ�ʵ��,���ܴ������ٸ�FCGI���Ӷ�������.

2012-3-15
ÿ��PHP-CGI���̶�Ӧһ���������Ƶ������ܵ�,��Ӧһ��FCGI����.
�������ĺô���HTTP����������ͨ��FCGI���ӵ�״̬�ж϶�Ӧ���Ǹ�PHP-CGI�����Ƿ����ڴ�������.
Ŀ����: FCGIFactory Ҫ�е��ԵĹ������ɸ�(����25��)PHP-CGI����,��ѹ���͵�ʱ��,�����������ٵ� PHP-CGI����,һ������ ���е�PHP-CGI������(�����е�FCGI������)����һ���ض���ֵ(����5��),��ɱ��һ������(����3��,ֻ����2�����н����ڿ��ж����ڵȴ���һ��ʹ��)���ҿ���ʱ�䳬��һ����ֵ(����5��)��PHP-CGI����.

2012-3-18
FCGIResponder
���������ΪFCGI server��ԭ��������ж�,��Ӧ�÷���һ�� FCGI_ABORT�����жϷ���.
�����黹��FCGIFactory�����ӾͿ�����������ʹ��.

2012-3-19
����ʹ�ûص�������ʵ��һ�ֺܲ��õ����,�Ժ����ĵ���˳��,·������Ҫ�ǳ����.
����������ͬ�����������,�����������.
�����Ƕ�Ӧ���������¼������ĳ����ûص���������ʲô�����취��? ������-������ģ��?
Խ��Խ��������ܹ�����Ҫ��,��ϧ�������̫��.

2012-3-23
Ϊ�˾�������FCGI�ű�������ʱ��,��Ҫ��������FCGI����Ӧ
1. �� memfile ���ڴ滺��.
2. �� tmpfile �ڴ����л���.

ͬ��Ҳ��Ҫ��������HTTP������
1. �� memfile ����.
2. post ���ļ���Ҫд����̵���ʱ�ļ�.

HTTP Server Ҫ����һ���ļ������ڴ����ʱ�ļ�.

HTTPRequest �Ƿ����յ���������֮��Żص� IHTTPserver onrequest?
���ȶ�,����� memcontent,������� file_content.

2012-3-24
ֻ��FCGIResponder��Ҫ���� request input, ����ֻ�� FCGIResponder �л�������.

2012-3-26
HTTPRequest �ڽ�����POST DATA֮��Żص�HTTPserver.

2012-4-1
"�˳���"
FCGI->Cache �� Cache->HTTP �����������������һֱ����,ֱ���д���������������ִ����ϲŽ���.
ÿ����������IO������ɵ�һ�̼�����һ����������״̬,���������һ���������Ѿ���������,���˳�.��"һ�̼�"�����˳���.

2012-4-6
1. FCGIResponder �˳�����:
1.1 ������һ���������ǰ
1.2 �������ʧ��ʱ

2. �Ự��ʱ���ʵ��
HTTPServerΪÿ�����ӷ���һ����ʱ��,��ʱ����ʱʱ,���� IRequest::stop() �� IResponder::stop(),���������Ȼ��ͬ��.

3. IOCPNetwork ����Ҫ������һ��ͬ������, onIoFinished �к�ʱɾ����ʱ���ȽϺ�?

2012-4-9
Ӧ���� mapServerFile() �д���Ĭ���ļ���������. ���� HTTPRequest, HTTPResponder, FCGIResponder �ȶ�����˵Ĭ���ļ�����͸����.

����ϵͳ��Ӧʹ�� fopen() ͬʱ�򿪵��ļ���������(2048),���֧�ָ���Ĳ�����������? �Ŷ�?
���� lighttpd ���ʵ��.

http://stackoverflow.com/questions/870173/is-there-a-limit-on-number-of-open-files-in-windows

If you use the standard C/C++ POSIX libraries with Windows, the answer is "yes", there is a limit.

However, interestingly, the limit is imposed by the kind of C/C++ libraries that you are using.

I came across with the following JIRA thread (http://bugs.mysql.com/bug.php?id=24509) from MySQL. They were dealing with the same problem about the number of open files.

However, Paul DuBois explained that the problem could effectively be eliminated in Windows by using ...

    Win32 API calls (CreateFile(), WriteFile(), and so forth) and the default maximum number of open files has been increased to 16384. The maximum can be increased further by using the --max-open-files=N option at server startup.

Naturally, you could have a theoretically large number of open files by using a technique similar to database connections-pooling, but that would have a severe effect on performance.

Indeed, opening a large number of files could be bad design. However, some situations call require it. For example, if you are building a database server that will be used by thousands of users or applications, the server will necessarily have to open a large number of files (or suffer a performance hit by using file-descriptor pooling techniques).

My 2 cents.

Luis

ֱ��ʹ�� Windows API ����/��/��д/�ر� �ļ� class WINFile ������ʹ�� C�����ļ� fopen ��. Ȼ����ʹ�õȴ����н�һ�����󲢷���.

2012-4-10
FCGIResponder ��2��ʹ���˴�ֲ������ĺ��� sendPostData() ֱ��ʹ�÷��ͻ��� reserve(), initFCGIEnv() Ҳ���,����ջ���.

2012-4-11
XmlDocument ������ʹ�õݹ麯���ĵط�ʹ��ջ��ѭ������.

2012-4-15
1. XmlDocument ���� xmlЭ��ڵ�ķ�ʽ��Ҫ������һ��.
2. XMLNode::GetNode ������Խ�������.

2012-4-16
��μ򵥵�֧�� XPath
1. ���ھ���·��ʹ�� /root/child1/child2
2. �������·��ʹ�� ./child1/child2 ���� nodename/child1/child2

Ŀǰ������������.

����һ�� class XPath 
1. ���캯������һ���ַ���.
2. bool GetFirst()
3. bool GetNext()
4. bool IsAbsolutePath()

���� 

XPath(const std::string &path, XmlDocument *doc);
XMLHANDLE XPath::GetNode();

����: XPath ��ֱ�Ӳ��� XmlDocument �û���ֻ���ṩ���� XPath �ַ����Ĺ��ܺ�?

2012-4-17
XMLNode ���뻹��UNICODE,�ò��� UTF-8?
OS_Conv() �Ľӿ��������
int OS_Conv("utf-8", "gb2312", src, srcLen, dest, destLen);
Windows ƽ̨�µľ���ʵ��Ҫ�������е����ı���.

====================
�Ľ�XMLģ��,�����ڴ��ʹ����
1. �������� LoadNode() ֱ�ӽ��� char�ַ�������.
2. �������� LoadNode() �ɷֿ����,ÿ��״̬�����Իָ�.
3. ������� GetNode() �ɷֿ����.

2012-4-22
v0.2��Ĺ����Ѿ�ʵ��.
1. IOCPNetwork �� XmlDocument �����໹��Ҫ�ٸĽ�.
2. XPath Ҫʵ��,���� xml ģ�����������������. ���ؽڵ㼯��ʱ��,��������������ָ��ļ���,����һ�� new �� listָ��, ��һ�����װ��,�������Զ�ɾ��.

===========================
2012-5-17
1.�������� FCGIResponder �������������Ĵ���,���ڵĴ���д��̫������.
2.���ȫ����ģʽ.
