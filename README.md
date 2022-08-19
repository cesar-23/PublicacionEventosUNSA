Proyecto final IS 

* César Carpio
* Jhon Sanchez
* Jheeremy Alvarez
* Diego rivas




controller.py --- restful
=================

REST is a style for network-based interactive applications that underlies the Web. The example here doesn't go over the network, but preserves the main contraints of REST, which are:
* Interactive: end-to-end between an active agent (e.g. a person) and a backend

* Separation between Client (user interface) and Server (data storage)

while True:
    # "server"-side computation
    state_representation, links = handle_request(*request)
    # "client"-side computation
    request = render_and_get_input(state_representation, links)

verify_user.py --- Monolithic
=================

No abstractions
No use of library functions

class RepositoryBase(object):
    def _init_(self, db):
        self.db = db

    def session(self):
        return self.db.session

    def create(self, item):
        self.session().add(item)
        self.session().commit()
showTable.py --- kick-forward
=================
Each function takes an additional parameter, usually the last, which is another function

    def normalize(str_data, func):
        func(str_data.lower(), remove_stop_words)


