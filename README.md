```Java
import javax.swing.*;
import java.awt.*;
import java.awt.event.ActionEvent;
import java.awt.event.ActionListener;

public class FormularioInicio extends JFrame {
    public FormularioInicio() {
        setTitle("Página de Inicio");
        setSize(300, 200); // Tamaño del formulario
        setLocationRelativeTo(null); // Centrar en pantalla
        setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        initComponents();
    }

    private void initComponents() {
        // Panel principal con layout
        JPanel panel = new JPanel();
        panel.setLayout(new GridLayout(6, 2)); // 6 filas, 2 columnas
        // Quitar el color de fondo azul
        // panel.setBackground(Color.BLUE);

        // Etiquetas y campos de texto
        JLabel lblUsuario = new JLabel("Usuario:");
        JTextField txtUsuario = new JTextField();
        JLabel lblCorreo = new JLabel("Correo Electrónico:");
        JTextField txtCorreo = new JTextField();
        JLabel lblContrasena = new JLabel("Contraseña:");
        JPasswordField txtContrasena = new JPasswordField();
        JLabel lblNumeroMovil = new JLabel("Número Móvil:");
        JTextField txtNumeroMovil = new JTextField();

        // Configuración del campo de contraseña para mostrar asteriscos
        txtContrasena.setEchoChar('*');

        // Añadir componentes al panel
        panel.add(lblUsuario);
        panel.add(txtUsuario);
        panel.add(lblCorreo);
        panel.add(txtCorreo);
        panel.add(lblContrasena);
        panel.add(txtContrasena);
        panel.add(lblNumeroMovil);
        panel.add(txtNumeroMovil);

        // Botones Aceptar y Cancelar
        JButton btnAceptar = new JButton("Aceptar");
        JButton btnCancelar = new JButton("Cancelar");

        // Agregar ActionListener al botón Aceptar
        btnAceptar.addActionListener(new ActionListener() {
            @Override
            public void actionPerformed(ActionEvent e) {
                JOptionPane.showMessageDialog(FormularioInicio.this, "Usuario registrado");
            }
        });

        // Botón para seleccionar categoría
        JButton btnBuscar = new JButton("¿Qué buscas?");
        btnBuscar.addActionListener(new ActionListener() {
            @Override
            public void actionPerformed(ActionEvent e) {
                String categoria = JOptionPane.showInputDialog(FormularioInicio.this, "Selecciona una categoría: Ropa, Objetos, Otros");
                if (categoria != null) {
                    JOptionPane.showMessageDialog(FormularioInicio.this, "Has seleccionado: " + categoria);
                }
            }
        });

        // Añadir botones al panel
        panel.add(btnAceptar);
        panel.add(btnCancelar);
        panel.add(btnBuscar);

        // Añadir panel al JFrame
        this.add(panel);
    }

    public static void main(String[] args) {
        SwingUtilities.invokeLater(new Runnable() {
            @Override
            public void run() {
                new FormularioInicio().setVisible(true);
            }
        });
    }
}
```
