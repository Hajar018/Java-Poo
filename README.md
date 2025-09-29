# Java-Poo
 TD 2 : encapsulation .
1/. Disque 
package td2TP;
//dans le fichier a crée pour la classe disque c'est un modéle 
//création la classe Disque et Une variable membre privé diamètre .
public class  Disque {
   private double  diamètre ;
//création Des constructeurs 
public Disque (){
};
public Disque (double d){
   this.diamètre = d;
};
public Disque(Disque d){
     this.diamètre = d.diamètre;
}
//création Une méthode modificatrice de diamètre 
public void SetDiamètre(double d){
     this.diamètre = d;
}
//création Une méthode sélectrice pour retourner le diamètre 
public double  GetDiamètre(){
     return diamètre;
}
//création Une méthode  pour calculer la  surface de disque 
// la surface = diamètre /2;
public double  Surface(){
     return math.Pi = math.pow(diamètre/2);
}
 //création Une méthode  pour calculer le rayon de disque 
public double  rayon(){
     return diamètre/2;
}
//création Une méthode  pour calculer le périmètre de disque 
public double  périmètre(){
     return math.Pi * diamètre ;
}
//création Une méthode pour afficher les caractéristiques du disque
 public void  Afficher(){
     System.out.println(" les caractéristiques du disque de diamètre"+diamètre+", Sruface : "+Surface()+" ," périmètre :"+périmètre()) ;
}
//  dans le fichier de class mainDisque pour tester et exécuter.
package td2TP;
// création 2 objets d1 et d2 de type Disque de diamètres d1(2.5), d2(5.6). 
public class mainDisque {

public static void main(String[] args) {
		Disque d1 = new Disque(2,5);
		Disque d2 = new Disque(5,6);
             d1.Afficher();
             d2.Afficher();
		

}

  }
}





2/. Classe CPoint3D : 
//création une classe CPoint3D  et définie par les coordonnées (x,y,z) 
public class  CPoint3D {
   private double  x ;
   private double  y ;
   private double  z ;
//création Des constructeurs 
public CPoint3D (){
};
public CPoint3D (double x ,  double y,  double z){
      this.x = x ;
      this.y = y; 
      this.z = z ;
};
public CPoint3D( CPoint3D a){
     this.x = a.x;
     this.y = a.y;
     this.z = a.z ;
}
//création de méthode  getters pour chaque coordonnées.
public double  getX(){
     return x;
}
public double  getY(){
     return y;
}
public double  getZ(){
     return z;
}
//création Une méthode modificatrice des coordonnées  de point.
public void setPoint(double x ,  double y,  double z){
     this.x = a.x;
     this.y = a.y;
     this.z = a.z ;
}
public void Déplacer(double dx ,  double dy,  double dz){
      x += dx;
      y += dy;
      z += dz ;
}
///création La méthode distance permet de calculer la distance du point par rapport à l’origine 
O(0,0,0) 
//dans java les nombre initialise automatiquement par 0.
public double  distance(){
     return Math.sqrt(x*x + y*y + z*z); ;
}
///création la méthode distance(CPoint3D) permet de calculer la distance du point par rapport à 
un autre point reçu comme paramètre. 
public double  distance(CPoint3D p1){
     return Math.sqrt((Math.pow(this.x - p1.x, 2) +
        Math.pow(this.y - p1.y, 2) +
        Math.pow(this.z - p1.z, 2));
} 
// La méthode egal permet de retourner true si le point est égal au point reçu comme 
paramètre.  
public boolean egal(CPoint3D p1) {
   if (this.x == x.p1 && this.y == y.p1 &&  this.z == z.p1){
         return true;
    }
   else{
       return false;
   }
}
//création Une méthode  pour afficher des coordonnées  de point
 public void afficher() {
        System.out.println("(" + x + ", " + y + ", " + z + ")");
    }
}
//une classe de test qui permet de : 
Créer 2 objets p1 et p2 de type CPoint3D de coordonnées p1(2, 5, 7), p2(5,9,16). 
 et D’afficher les caractéristiques des 2 points, ainsi que la distance qui les sépare. 
public class TestPoint3D {
    public static void main(String[] args) {
// Créer deux objets  points
        CPoint3D p1 = new CPoint3D(2, 5, 7);
        CPoint3D p2 = new CPoint3D(5, 9, 16);

// Affichage pour chaque point et ses coordonnées.
        System.out.print(" La Point p1: ");
        p1.afficher();
        System.out.print(" La Point p2: ");
        p2.afficher();

// Distance de p1 à l'origine
        System.out.println("Distance de p1 à l'origine: " + p1.distance());

// Distance entre p1 et p2
        System.out.println("Distance entre p1 et p2: " +p1.distance(p2));

// faire la comparaison pour savoir le point est égal au point reçu comme paramètre.
        System.out.println("p1 égal à p2 sont égaux ou pas :" + p1.egal(p2));
    }
}





3/.  CSphere 
//création  la  classe CSphere 
public class CSphere {
    private CPoint3D centre;
    private double rayon;
//création   des Constructeurs
    public CSphere() {
    
  }
  public CSphere(double x, double y, double z, double rayon) {
        this.centre = new CPoint3D(x, y, z);
        this.rayon = rayon;
    }

  public CSphere(CPoint3D centre, double rayon) {
        this.centre = centre;
        this.rayon = rayon;
    }

// création  des  getters
    public double getRayon() { 
        return rayon; 
}
    public CPoint3D getCentre() { 
        return centre;
 }
//  création  des setters
    public void setSphere(CPoint3D centre, double rayon) {
        this.centre = centre;
        this.rayon = rayon;
    }
//    création  méthode surface   permet de calculer  Surface = 4*pi*r*r;
    public double surface() {
        return 4 * Math.Pi * Math.pow(rayon, 2);
    }
// création  méthode  volume  permet de calculer Volume = (4/3 )* pi *(r*r*r);
    public double volume() {
        return (4 / 3) * Math.PI * Math.pow(rayon, 3);
    }

// Affichage les  caractéristiques de  CSphere
    public void afficher() {
        System.out.println("Les Caractéristiques de la CSphere sont : ");
        centre.afficher();
        System.out.println(" le Rayon  = " + rayon);
        System.out.println("la Surface = " + surface());
        System.out.println("le Volume = " + volume());
    }
}

TD 3 : héritage . 
//création de classe mére s'appelle Personne 
package heritageTd3;

public class Personne {
	protected String nom;
	protected  byte age;
	
	
public  Personne() {
		
}
public  Personne(String nom, byte age ) {
		this.age = age;
		this.nom = nom;
		
}
public Personne( Personne a) {
		this.age = a.age;
		this.nom = a.nom;
	}
	public void setPersonne(String nom, byte age ) {
		this.age = age;
		this.nom = nom;
	}
	public String getNom() {
		return nom;
	}
	public byte getAge() {
		return age;
	}
	public String toString() {
		return "Personne [nom=" + nom + ", age=" + age + "]";
	}

}
//création d'une classe Personnel qui hérite de la classe Personne
package heritageTd3;

public class Personnel extends Personne {
	protected  String adress ;
	protected  float salaire;
	
	
public Personnel() {
		 
}
public Personnel(String nom, byte age,  String adress,  float salaire) {
		super( nom,age);
		this.adress = adress ;
		this.salaire = salaire;
		
}
public Personnel(Personnel A) {
		 super(A.getNom(),A.getAge());
                  this.adresse = p.adresse;
                  this.salaire = p.salaire;
	 }
       public void setPersonnel(String nom, byte age,  String adress,  float salaire) {
                setPersonne(nom, age);
		this.adress =  adress;
		this.salaire =  salaire;
	}
        public String  getAdresse() {
		return adress;
	}
       public float  getSalaire() {
		return salaire;
	}
     public String toStringP() {
		return "Personnel :[super.toString()+ ", Adreess="+adress+" , salaire= "+salaire];
	}
// Création d'une classe Enseignant qui hérite de la classe Personnel 
public class Enseignant extends Personnel {
   private String  matiereEnseignant ;
   public   Enseignant() {
		
   }
   public  Enseignant(String nom, byte age,  String adress,  float salaire, String  matiereEnseignant ) {
		super( nom,age, adress,salaire);
		this.matiereEnseignant = matiereEnseignant ;
		
}
         public Enseignant (Enseignant  E) {
		 super(E.getNom(),E.getAge(),E.getAdresse(),E.getSalaire());
                  this.matiereEnseignant = E.matiereEnseignant ;

}
      public void setEnseignant(String nom, byte age,  String adress,  float salaire,  String  matiereEnseignant ) {
                setPersonne(nom, age);
                 setPersonnel(adress, salaire);
		this.matiereEnseignant =  matiereEnseignant;
		
}
         public String getMatiereEnseignant() {
		return matiereEnseignant;
	}
         public String toString() {
		return "Enseignant:[super.toString()+toStringP+", matiereEnseignant="+matiereEnseignant];
	}

   





}

ce fichier contient quelque exercice de  concept de  Classes , encapsulation  et  héritage
