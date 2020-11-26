# Penghubung
    from paramiko.client import SSHClient,AutoAddPolicy
    from getpass import getpass
    paswd = getpass()

    client = SSHClient()
    client2 = SSHClient()

    client.set_missing_host_key_policy(AutoAddPolicy())
    client.connect("192.168.100.144",22,"user",paswd)

    while(True):
        stdin,stdout,stderr = client.exec_command('python3 tugas.py')

        lines = stdout.readlines()
        lines_err = stderr.readlines()


        for i in lines_err:
           print(i)
        for i in lines:
           print(i)

    client.close()
    client2.close()
