
controller.py --- restful
-----------------------------

from blogex_app import Context

if _name_ == "_main_": Context.setup()

presentation.py --- Cook Book
=================

from jinja2 import Undefined
from jinja2.filters import do_mark_safe

def linebreaksp(text):
    if text is None or isinstance(text, Undefined):
        return text 
    text = "<p>" + text.replace('\n', '</p><p>') + "</p>"
    return do_mark_safe(text)

def register_filters(app):
    app.jinja_env.filters['linebreaksp'] = linebreaksp

orm_repository_base.py --- Monolithic
=================

class RepositoryBase(object):
    def _init_(self, db):
        self.db = db

    def session(self):
        return self.db.session

    def create(self, item):
        self.session().add(item)
        self.session().commit()
