<h1><center>Gabriel Mendoza Garcia</center></h1>
<hr>
<h2> Datos Principales: </h2>
<h3> Estudios: Ing. En Sistemas de Computo </h3>
<h3> Puesto Actual </h3>
<ul><li>Administrador de Base de Datos</li></ul> 
<h3> Experiencia Laboral: </h3>

<ul> 
<li>Detectar, solucionar problemas y documentar fallas del software y hardware.</li>
<li>Proveer soporte en el manejo de programas/aplicaciones.</li>
<li>Proveer ayuda al usuario de la mejor manera, para que use los recursos de computación disponibles.</li>
<li>Proveer soporte básico para el equipo de hardware.</li>
<li>Ayuda a actualizar el inventario del hardware y software.</li>
<li>Desarrollar y mantener correctamente la documentación y mapas de la red.</li>
<li>Buenas habilidades de organización; establecer prioridades realistas y conocer las fechas límites; capaz de realizar varias tareas a la vez; entrega de trabajaos de calidad.
</li> 
</ul> 

<img src="Foto1.jpg" alt="MiFoto" width="230" height="300">

<br>
<br>
<hr>
<h3> Indice </h3>
<A href="#Diario">Diario de campo</A>
<br><A href="#Documentos">Documentos</A>
<br><A href="#Reproducciones">Reproducciones</A>
<br><A href="#Desarrollo">Desarrollo de una Solución Java OO</A>
<br><A href="#Reflexiones">Reflexiones y autoevaluación</A>
<br>
<br>
<hr>


<A name="Diario"><h3> Diario de campo: </h3> </A>
Objetivo personal:
Superarme en todos los aspectos de mi vida, brindando lo mejor de mí cada día, 
tanto en el aspecto laboral como en el aspecto personal.

Reflexiones: 

Aplicacion distribuida es una aplicación con distintos componentes 
que se ejecutan en entornos separados, normalmente en diferentes plataformas 
conectadas a través de una red. 

Las típicas aplicaciones distribuidas son de dos niveles (cliente-servidor), 
tres niveles (cliente-middleware-servidor) y multinivel.

Criterios de evaluación propios. 
Consideraria que mi desempeño fue bueno durante 
el tiempo que duro la clase, soy capas y dedicado al realizar las actividades 
y foros. Presente problemas por lo tiempos ya que en muchas ocasiones tuve que 
trabajar mas del horario por temas de cierre de proyectos.


<img src="Pregunta1.jfif" alt="Apli Distr" width="400" height="500">



<A name="Documentos"><h3> Documentos: </h3> </A>

Coloco los entregables realizados durante la clase.
<br>
<a href="Entregable1.docx">
<img src="Word.png" alt="Apli Distr" width="100" height="100">
</a>
<br>
<b>Entregable 1</b>
<br>
<a href="Entregable2.doc">
<img src="Word.png" alt="Apli Distr" width="100" height="100">
</a>
<br>
<b>Entregable 2</b>



<A name="Reproducciones"><h3> Reproducciones:</h3> </A>

Referencias sobre Aplicaciones distribuidas:

<br>

<a href=http://heybd.blogspot.com/2011/03/que-es-uml.html>
<img src="uml.jpg" alt="Apli Distr" width="100" height="100">
</a>
<br>
<b>Link UML</b>
<br>



<br>
<b>Platica APP Distribuidas</b>
<br>












<A name="Desarrollo"><h3> Desarrollo de una Solución Java OO: </h3> </A>

Anexo codigo, se creo en netbeans swing.

import java.awt.*;
import java.awt.event.*;
import javax.swing.*;
import javax.swing.border.*;
import javax.swing.event.*;
import java.text.*;
 
public class MenuCena extends JFrame implements ItemListener, ActionListener
{
	String platos[] =   {"Entrantes","Carnes","Pescados","Postres","Bebidas","Cafe-Copa"};
	String variedades[][]={
				{"Jamon","Marisco","Ensalada","QuitaGranos"},
				{"Ternera","Chuleton","Pato a la naranja","Filete de cerdo","OsoBuco","Filete Plancha"},
				{"Merluza en salsa","Bacalao al pil pil","Besugo"},
				{"Tarta al wiski","Helado","Postre de la casa"},
				{"Vino Blanco","Vino Tinto","Agua","Cerveza"},
				{"solo","cortado","con leche","pacharan","whisky","nada"}
			};
	String precio[][]={	{"12","15.5","6.3","20"},
							{"10.0","15.5","9.90","2.5","4.5","4.5"},
							{"9.9","10","14"},
							{"3","3","4"},
							{"7","8","2.5","4"},
							{"1","1.1","1.2","3","4","0"}
 };
	ButtonGroup gb[]= new ButtonGroup[platos.length];
	JPanel p,p1,p2,p3,p4,p2i[]= new JPanel[gb.length];
	JButton b1,b2,b3,b4;
	JTextArea ta;
	JScrollPane tajsp;
	JScrollPane jsp;
	JRadioButton rb[][];//= new JRadioButton[platos.length][variedades[5].length];
	JCheckBox cb[]= new JCheckBox[platos.length];
	boolean agotado[][];
	BorderLayout bl;
	Font negro,rojo;
 
	public MenuCena()
	{	int i,j;
		Insets insets= new Insets(65,50,65,50);
		p =new JPanel(new GridLayout(4,1));
		p2=new JPanel(new GridLayout(1,gb.length));
		p1=new JPanel(new GridLayout(1,1));
		for(i=0;i<gb.length;i++)
		{
			p2i[i]=new JPanel(new GridLayout(variedades.length,1));
			p2i[i].setBorder(BorderFactory.createTitledBorder(
BorderFactory.createEtchedBorder(),platos[i]));
		}
		p3=new JPanel(new GridLayout(1,1));
		p4=new JPanel(new BorderLayout());//new GridLayout(1,1));
 
		// panel 1		
		for(i=0;i<cb.length; i++)
		{
			cb[i]= new JCheckBox(platos[i]);
			cb[i].addItemListener(this);
			cb[i].setBackground(Color.green);
			p1.add(cb[i]);
		}
 
		// panel 2		
		rb= new JRadioButton[platos.length][];
		agotado = new boolean[platos.length][];
		for(i=0;i<platos.length;i++)
		{	rb[i]= new JRadioButton[variedades[i].length];
			agotado[i]= new boolean[variedades[i].length];
		}
		for(i=0;i<gb.length; i++)
		{
			gb[i]= new ButtonGroup();
	for (j=0; j<variedades[i].length; j++)
			{
				rb[i][j]= new JRadioButton(variedades[i][j],false);
				agotado[i][j]= false;
				rb[i][j].addItemListener(this);
				rb[i][j].setEnabled(false);
				gb[i].add(rb[i][j]);
				p2i[i].add(rb[i][j]);
				rb[i][j].setBackground(Color.cyan);
				rb[i][j].setToolTipText(variedades[i][j]+"-->"+precio[i][j]);
			}
			rb[i][0].setSelected(true);
			p2.add(p2i[i]);
		}
 
		// Panel 3  area de texto.
		ta = new JTextArea(" CAFETERIA CANDY ELIJA un menu.",15,40);
		ta.setBackground(Color.green);
		ta.setBorder(BorderFactory.createTitledBorder(BorderFactory.createBevelBorder(BevelBorder.LOWERED ),"MENU ELEGIDO"));//createEtchedBorder(),"MENU ELEGIDO"));
		ta.setEditable(false);
		tajsp = new JScrollPane(ta);
	//	try{		
		tajsp.setVerticalScrollBarPolicy(JScrollPane.VERTICAL_SCROLLBAR_ALWAYS);
		tajsp.setHorizontalScrollBarPolicy(JScrollPane.HORIZONTAL_SCROLLBAR_ALWAYS);
	//	}catch(IllegalArgumentException iae){ta.append("Argumento ilegal");}
		//panel 4 Botones
		b1 = new JButton("SELECCIONAR ");
		b2 = new JButton("DETO NO KEDA");
		b3 = new JButton("    REPONER    ");
		b4 = new JButton("    SALIR   ");
		b3.setBackground(Color.red);
		b1.setBackground(Color.green);
		b2.setBackground(Color.white);
 
		b1. setMargin(insets);
		b2. setMargin(insets);
		b3. setMargin(insets);
		b1.addActionListener(this);
		b2.addActionListener(this);
		b3.addActionListener(this);
		b4.addActionListener(new ActionListener(){public void actionPerformed( ActionEvent aw)
				{System.exit(-2);	}});
 
		p4.add(b3,BorderLayout.WEST);
		p4.add(b1,BorderLayout.CENTER);
		p4.add(b2,BorderLayout.EAST);
		p4.add(b4,BorderLayout.SOUTH);
 
		p3.add(tajsp);// area de texto con deslizadores.
		p.add(p1);		p.add(p2);		p.add(p3);		p.add(p4);
	this.getContentPane().add(p);
	}
 
	public void itemStateChanged(ItemEvent ie)
	{
		Object o;
		o=ie.getSource();
		if (o instanceof JCheckBox)
		{
			for(int i=0;i<platos.length;i++)
			{
				if((JCheckBox)ie.getItemSelectable()==cb[i])
					if(((JCheckBox)o).isSelected())
						activarBotonera(i,variedades[i].length, true);
					else
						activarBotonera(i,variedades[i].length,false);
			}
		}
	}
 
	private void activarBotonera(int k,int n,boolean sw)
	{
		for(int i=0; i<n;i++)
	if(sw && !agotado[k][i])	rb[k][i].setEnabled(true);
			else	rb[k][i].setEnabled(false);
	}
 
	public void actionPerformed(ActionEvent ae)
	{
		NumberFormat formato ;
		double tot,x;
		int i,j;
		formato =  NumberFormat.getNumberInstance();
		formato.setMaximumFractionDigits(2);
		formato.setMinimumFractionDigits(2);
		formato.setMinimumIntegerDigits(3);
		if(ae.getSource() instanceof JButton)
		{
			if(((JButton)ae.getSource())==b1)	// SELECCIONAR
			{	// borrar pantalla previa
				ta.setText("");
				tot=0;
				for(i=0;i<platos.length;i++)
				{
					if(cb[i].isSelected())
						for(j=0; j<variedades[i].length;j++)
							if(!agotado[i][j] && rb[i][j].isSelected())
							{	x=Double.parseDouble(precio[i][j]);
								ta.append("precio   :    "+formato.format(x)+" ¦  "+cb[i].getText() + ": " + rb[i][j].getText()+"\n");
								tot += x;
							}
				}
				double iva = tot*.7;
				ta.append("TOTAL =    "+ formato.format(tot)+"\nIVA (7%) = "+ formato.format(tot*.07));//iva));
				ta.setForeground(Color.red);
				ta.append( "\nFACTURA="+formato.format(tot*1.07));
				repaint();
				ta.setForeground(Color.BLUE);
			}
			else if(((JButton)ae.getSource())==b2) // AGOTADO 
			{
				for(i=0;i<platos.length;i++)
					if(cb[i].isSelected())
						for(j=0; j<variedades[i].length;j++)
							if( rb[i][j].isSelected())
							{	agotado[i][j] =true;
								rb[i][j].setEnabled(false);
							}
			}
			else  if(((JButton)ae.getSource())==b3) // REPONER
			{
				for(i=0;i<platos.length;i++)
					if(cb[i].isSelected())
						for(j=0; j<variedades[i].length;j++)
						{
							// reponer todos.
							//if(!rb[i][j].isEnabled() && agotado[i][j])  // no se pueden seleccionar si desactivados
							{
								agotado[i][j] =false;
								rb[i][j].setEnabled(true);
							}
						}
			}
		}
	}
	public static void main(String[]args)
	{
		MenuCena mn= new MenuCena();
		mn.addWindowListener(new WindowAdapter(){
			public void windowClosing(WindowEvent we)
			{	System.exit(1);	}});
		mn.setSize(600,800);
		mn.setResizable(false);
		mn.setVisible(true);
	}
}



<A name="Reflexiones"><h3> Reflexiones y autoevaluación:</h3> </A>incluye a manera de ensayo las reflexiones y
autoevaluación de tu proceso de aprendizaje en la materia, dando
respuesta a las siguientes 15 cuestiones:
<br>
<br> ¿Qué aprendiste? ¿Qué te falta por aprender?
<br> ¿Cómo aplicarás lo aprendido en tu vida profesional?
<br> ¿Cómo fue tu proceso personal de aprendizaje?
<br> ¿Qué aprendiste de tu profesor?
<br> ¿Qué aprendiste de las actividades?
<br> ¿Qué aprendiste de los contenidos y recursos del curso?
<br> ¿Qué aprendiste de tus colegas?
<br> ¿Qué aprendiste de ti mismo?
<br> ¿Cómo aprovechaste los contenidos y recursos ofrecidos por el profesor? ¿Por qué?
<br> ¿Cómo aprovechaste la retroalimentación dada por el profesor? ¿Por qué?
<br> ¿Cómo aprovechaste los canales de comunicación con el profesor? ¿Por qué?
<br> ¿Cómo aprovechaste las actividades de aprendizaje? ¿Por qué?
<br> ¿Cómo aprovechaste la comunicación con tus colegas? ¿Por qué?
<br> ¿Cómo mejoraría tu proceso de aprendizaje?
<br> ¿Cuál es tu opinión acerca del curso?


<br>




</HTML>
