# systemd

O systemd é um gerenciador de serviços. Ele é executado logo depois que o kernel é inicializado, por isso ele possui o PID (process id) 1. A sua função é inicializar e manter os serviços do espaço do usuário.

# service units

Service unit é uma entidade que é configurada por meio de um arquivo (unit file) terminado em ".service", esse arquivo contém informação de um processo que é supervisionado e controlado pelo systemd. Quando um serviço/processo é controlado pelo systemd, é possível inicializar, para, reiniciar, ativar e desativar a inicialização automática após a inicialização, entre outros.

# target units

Target é basicamente estados de um sistema, por exemplo, graphical.target é quando o sistema está funcionando em sua forma com interface, multi-user.target é quando o sistema está funcionando somente em linha de comando etc. O Linux define essas etapas, e é possível dizer que um service é requerido para um desses targets, por exemplo, não faz sentido rodar o nginx em um target que não tenha a rede configurada. Existe diversos tipos de target, outro legal é o de diretório, que permite fazer a dependência de um service com a existência de um diretório.
