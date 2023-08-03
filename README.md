# Habilitar múltiples sesiones RDP en Windows XP.

Zip a usar por version de Windows:

Windows XP RTM SP1 y SP2: termsrv.dll_RTM.zip
Windows XP SP2: termsrv.dll_SP2.zip
Windows XP SP3: termsrv.dll_SP3.zip

# 1 - Parar servicio "Terminal Services":

sc queryex TermService\n
taskkill /F /PID PID_SERVICIO_ANTERIOR

# NOTA: Tras parar los servicios, tendrás 1 minuto para realizar las siguientes acciones.

# 2 - Backup del fichero termsrv.dll y copia del nuevo archivo dll:

Entrar en %windir%\System32 y renombrar, si existe, el archivo termsrv.dll a termsrv_back.dll. Luego copiar el termsrv.dll descargado.

Entrar en %windir%\System32\dllcache y renombrar, si existe, el archivo termsrv.dll a termsrv_back.dll. Luego copiar el termsrv.dll descargado.

# 3 - Ejecutar el bat CCreg.bat con permisos de administrador.

# 4 - Entrar en gpedit.msc y hacer lo siguiente:

Entrar en la siguiente ruta: Configuración del equipo -> Plantillas administrativas -> Componentes de Windows -> Terminal Services -> Habilitar limitar el número de conexiones y asignar un numero de 2 o 3 sesiones.

# 5 - Habilitar cambio rápido de usuarios:

Inicio -> Panel de control -> Cuentas de usuario -> Cambiar la forma en que los usuarios inician y cierran sesión.

# 6 - Reiniciar MV.

# NOTA: Si la máquina está en un dominio, habría que añadir el bat a la carpeta C:\Documents and Settings\All Users\Start Menu\Programs\startup para que no se modifiquen los registros en caso de reinicio u otra cosa imprevista.
