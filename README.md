import kivy
from kivy.app import App
from kivy.uix.gridlayout import GridLayout
from kivy.uix.label import Label
from kivy.uix.button import Button
from kivy.uix.widget import Widget
from kivy.lang import Builder
from kivy.core.window import Window
from kivy.uix.button import Button
from kivy.uix.screenmanager import ScreenManager, Screen
from kivy.properties import ObjectProperty
from kivy.uix.popup import Popup 

class Widgets(Widget):
      def btn2(self):
            show_popup()


class MainWindow(Screen):
      pass

class SecondWindow(Screen):
      pass

class ThirdWindow(Screen):
      address = ObjectProperty(None)
      email = ObjectProperty(None)

      def btn(self):
          print("Address:", self.address.text, "Email:", self.email.text) 
          self.address =""
          self.email =""

class FourthWindow(Screen):
      pass
          
class WindowManager(ScreenManager):
      pass

kv = Builder.load_file('my.kv')

class MyLayout(Widget):
      pass

class P(GridLayout):
      pass

class MyApp(App):
        
        def build(self):
            Window.clearcolor =(1,1,1,1)
            return kv

def show_popup():
      show = P
      
      popupWindow = Popup(title="Popup Window", content=show, size_hint=(None,None), size=(400,400))
  
      popupWindow.open()
if __name__ == "__main__":
    MyApp().run()
